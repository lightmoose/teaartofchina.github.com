(function() {
  var __sections__ = {};
  (function() {
    for(var i = 0, s = document.getElementById('sections-script').getAttribute('data-sections').split(','); i < s.length; i++)
      __sections__[s[i]] = true;
  })();
  (function() {
  if (!__sections__["promo-fixed"]) return;
  try {
    
  function initPromoFixed(){
    var $ttpromofixed = $(".tt-promo-fixed"),
    	$promofixeddata = $(".promofixeddata"),
        $promofixedclose = $ttpromofixed.find(".tt-btn-close");
    
    if($('html').hasClass('touch-device') && $ttpromofixed.hasClass('hidden-mobile')) return false;
	if($ttpromofixed.hasClass('hidden-mobile') && $(window).width < 1025) return false;
    if($promofixeddata.length == 0) return false;
    
    setPromoFixedItem($ttpromofixed, $promofixeddata);
	showPromoFixed($ttpromofixed, $ttpromofixed.data('start'));
    
	showPromoFixedNextMessage($ttpromofixed, $promofixeddata, $promofixedclose)

    $promofixedclose.click(function(){
      $ttpromofixed.addClass('nonevent').fadeTo(100, 0);
    });
  }
  function showPromoFixedNextMessage($modal, $data, $close){
    var nextmin = $modal.data('min'),
        nextmax = $modal.data('max');
	var i = getRndInteger(nextmin, nextmax);
    setTimeout(function(){
      $close.trigger('click');
      setTimeout(function(){
        setPromoFixedItem($modal, $data);
        showPromoFixed($modal, 0);
        showPromoFixedNextMessage($modal, $data, $close);
      }, 100);
    }, i);
  }
  function getPromoFixedCustomProductIndex($promofixeddata){
    var min = 0,
        max = $promofixeddata.children().length;
    return getRndInteger(min, max);
  }
  function setPromoFixedItem($modal, $data){
    var i = getPromoFixedCustomProductIndex($data)
    var data = $data.children().eq(i);
    $modal.find('.tt-img').find('a').attr('href', data.data('url')).find('img').attr('src', data.data('image')).attr('alt', data.data('alt'));
    $modal.find('.pr_name').attr('href', data.data('url')).text(data.data('name'));
    
    var nummin = parseInt(data.data('min')),
    	nummax = parseInt(data.data('max')),
    	num = getRndInteger(nummin, nummax);
    $modal.find('.tt-info-value').text(num);

	if (typeof data.data('text') === typeof undefined) return false;
    var str = data.data('text').split('||'),
    	i = getRndInteger(0, str.length-1);
    $modal.find('.tt-info-text').text(str[i]);
  }
  function showPromoFixed($parent, delay){
    setTimeout(function(){
	  $parent.removeClass('nonevent').fadeTo(300, 1);
    }, delay);
  }
  function getRndInteger(min, max) {
    return Math.floor(Math.random() * (max - min) ) + min;
  }
  setTimeout(initPromoFixed, 300);

  } catch(e) { console.error(e); }
})();

})();
