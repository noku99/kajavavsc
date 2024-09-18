
var idn = '/static/js/locale/idn.js'
var en_us = '/static/js/locale/en_us.js'
var vi = '/static/js/locale/vi.js'
var spanish = '/static/js/locale/spanish.js'
var russian = '/static/js/locale/russian.js'
var portuguese = '/static/js/locale/portuguese.js'
var thailand = '/static/js/locale/thailand.js'
var arabic = '/static/js/locale/arabic.js'
var filipino = '/static/js/locale/filipino.js'
var turkey = '/static/js/locale/turkey.js'

var init = false

// å›¾ç‰‡åŸŸå
var wwwhost = 'https://www.happywifis.com';
if(location.host.indexOf('webtest') > -1){
    wwwhost = 'https://wwwtest.happywifis.com'
}
window.wwwhost = wwwhost
window.imgPath = wwwhost+'/activity/locales_imgs'

var loadLocale = function(callback, language){
    if(callback){
        this.callback = callback;
    }
    if(getQueryString('language')){
        language = getQueryString('language')
    }
    if(!init && !language){
        return callGetAppLanguage();
    }
    var lang = language || getStoregeDaga('local_locale')
    var url = '';
    /**
     * 1 è²å¾‹å®¾ 2 è¶Šå— 3 å°å°¼ 4 è¥¿ç­ç‰™ 5 å¢¨è¥¿å“¥ 6å“¥ä¼¦æ¯”äºš 7 æ ¹å»· 8 ç§˜é² 9å†…ç‘žæ‹‰ 10 'ç¾Žå›½ï¼ˆè‹±æ–‡ï¼‰  11  æ–°åŠ å¡ï¼ˆè‹±æ–‡ï¼‰  12 é©¬æ¥è¥¿äºšï¼ˆè‹±æ–‡ï¼‰ 13 å·´è¥¿ï¼ˆè‘¡è„ç‰™è¯­ï¼‰ 14 ä¿„ç½—æ–¯ 15ä¸­æ–‡ 17æ³°è¯­
     * 18å°¼æ—¥åˆ©äºšï¼ˆè‹±æ–‡ï¼‰ 19æ²™ç‰¹é˜¿æ‹‰ä¼¯ï¼ˆé˜¿æ‹‰ä¼¯è¯­ï¼‰ 20åŸƒåŠï¼ˆé˜¿æ‹‰ä¼¯è¯­ï¼‰ 21é˜¿è”é…‹ï¼ˆé˜¿æ‹‰ä¼¯è¯­ï¼‰22è²å¾‹å®¾ 23åœŸè€³å…¶
    */
    lang = parseInt(lang)

    switch(lang){
        case 0:
        case 10:
        case 11:
        case 12:
        case 18:
        case 1: url = en_us; break;
        case 2: url = vi; break;
        case 3: url = idn; break;
        case 4:
        case 5:
        case 6:
        case 7:
        case 8:
        case 9: url = spanish; break;
        case 13: url = portuguese; break;
        case 14: url = russian; break;
        case 17: url = thailand; break;
        case 19:
        case 20:
        case 21: 
            url = arabic;
            // æ·»åŠ æ ·å¼
            $('body').css('direction', 'rtl')
            $('#app').addClass('arabic')
        break;
        case 22: url = filipino; break;
        case 23: url = turkey; break;
        default:
            url = en_us;
    }

    url += '?t='+Date.now();
    var script = document.createElement('script');
    script.setAttribute('type', 'text/javascript');
    script.setAttribute('src', url);
    document.getElementsByTagName('head')[0].appendChild(script);
    script.addEventListener('load', ev => {
        this.callback && this.callback(locale, lang)
    });
}

// currency_location: ç¬¦å·åœ¨å‰  1 ç¬¦å·åœ¨åŽ
var moneyConfig = [
    { id: 0, money_emoji: '$', currency_location: 0, title: 'éžåœ°åŒºï¼ˆè‹±æ–‡ï¼‰' },
    { id: 1, money_emoji: 'â‚±', currency_location: 0, title: 'è²å¾‹å®¾/è‹±' },
    { id: 2, money_emoji: 'â‚«', currency_location: 1, title: 'è¶Šå—' },
    { id: 3, money_emoji: 'Rp', currency_location: 0, title: 'å°å°¼' },
    { id: 4, money_emoji: '$', currency_location: 0, title: 'è¥¿ç­ç‰™' },
    { id: 5, money_emoji: '$', currency_location: 0, title: 'å¢¨è¥¿å“¥' },
    { id: 6, money_emoji: '$', currency_location: 0, title: 'å“¥ä¼¦æ¯”äºš' },
    { id: 7, money_emoji: '$', currency_location: 0, title: 'é˜¿æ ¹å»·' },
    { id: 8, money_emoji: '$', currency_location: 0, title: 'ç§˜é²' },
    { id: 9, money_emoji: '$', currency_location: 0, title: 'å§”å†…ç‘žæ‹‰' },
    { id: 10, money_emoji: '$', currency_location: 0, title: 'ç¾Žå›½ï¼ˆè‹±æ–‡ï¼‰' },
    { id: 11, money_emoji: '$', currency_location: 0, title: 'æ–°åŠ å¡ï¼ˆè‹±æ–‡ï¼‰' },
    { id: 12, money_emoji: '$', currency_location: 0, title: 'é©¬æ¥è¥¿äºšï¼ˆè‹±æ–‡ï¼‰' },
    { id: 13, money_emoji: 'R$', currency_location: 0, title: 'å·´è¥¿ï¼ˆè‘¡è„ç‰™è¯­ï¼‰' },
    { id: 14, money_emoji: 'â‚½', currency_location: 1, title: 'ä¿„ç½—æ–¯' },
    { id: 15, money_emoji: 'ï¿¥', currency_location: 0, title: 'ä¸­å›½' },
    { id: 17, money_emoji: 'â‚¦', currency_location: 0, title: 'å°¼æ—¥åˆ©äºšï¼ˆè‹±æ–‡ï¼‰' },
    { id: 18, money_emoji: '$', currency_location: 0, title: 'æ²™ç‰¹é˜¿æ‹‰ä¼¯ï¼ˆé˜¿æ‹‰ä¼¯è¯­ï¼‰' },
    { id: 19, money_emoji: '$', currency_location: 0, title: 'åŸƒåŠï¼ˆé˜¿æ‹‰ä¼¯è¯­ï¼‰' },
    { id: 20, money_emoji: 'Ø¯.Ø¥', currency_location: 0, title: 'é˜¿è”é…‹ï¼ˆé˜¿æ‹‰ä¼¯è¯­ï¼‰' },
]
// èŽ·å–è´§å¸é…ç½®
function getUserMoneyConfig(language){
    var result = moneyConfig[0]
    moneyConfig.map(function(d){
        if(d.id == language){
            result = d;
        }
    })
    return result;
}

function toLoadLocale(lang, version){
    if(lang){
        setStoregeDaga('local_locale', lang)
        setStoregeDaga('version', version)
    }
    loadLocale();
}

// èŽ·å–appè¯­è¨€è®¾ç½®
function callGetAppLanguage() {
    init = true;
    if(!window.webkit && !window.happywifi){
        toLoadLocale();
        return;
    }
    try {
        if (isIos()) {
            window.webkit.messageHandlers.callGetAppLanguage.postMessage('toLoadLocale');
        } else {
            window.happywifi.callGetAppLanguage('toLoadLocale');
        }
    } catch (error) {
        toLoadLocale('3', '2.0.0');
    }
}

// åˆ¤æ–­è®¾å¤‡ä¸º ios
function isIos() {
    var u = navigator.userAgent;
    if (u.indexOf("iPhone") > -1 || u.indexOf("iOS") > -1) {
        return true;
    }
    return false;
}

function setStoregeDaga(key, value){
    try {
        localStorage.setItem(key, value)
    } catch (error) {
        
    }
}

function getStoregeDaga(key){
    try {
        return localStorage.getItem(key)
    } catch (error) {
        return null
    }
}

function getQueryString(name) {
    var reg = new RegExp("(^|&)" + name + "=([^&]*)(&|$)", "i");
    var str = location.href.split('?')[1] || '';
    var r = str.match(reg);
    if (r != null) return unescape(r[2]);
    return null;
}