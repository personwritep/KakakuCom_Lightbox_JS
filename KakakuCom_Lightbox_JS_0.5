// ==UserScript==
// @name        KakakuCom Lightbox JS
// @namespace        http://tampermonkey.net/
// @version        0.5
// @description        価格.COMのユーザー投稿画像を高精細拡大表示
// @author        価格.COMユーザー
// @match        https://*.kakaku.com/*
// @icon        https://www.google.com/s2/favicons?sz=64&domain=kakaku.com
// @noframes
// @grant        none
// @updateURL        https://github.com/personwritep/KakakuCom_Lightbox_JS/raw/main/KakakuCom_Lightbox_JS.user.js
// @downloadURL        https://github.com/personwritep/KakakuCom_Lightbox_JS/raw/main/KakakuCom_Lightbox_JS.user.js
// ==/UserScript==


let disp_mode=0; // 拡張ディスプレイモードの判別
let c_press=false; // Ctrlキー押下フラグ
let position_y=0; // ページのスクロール位置

let view_w=get_cookie('KCL_w')*1; // 拡大率
if(!view_w){
    view_w=500; // 🔴拡大率の初期値
    document.cookie='KCL_w='+ view_w +'; path=/; Max-Age=259200'; } // 3日間有効

let html_=document.documentElement;
let help_url='https://ameblo.jp/personwritep/entry-12966963082.html';


document.addEventListener('mousedown', function(event){
    if(disp_mode==0){ // Lightbox非表示
        if(event.ctrlKey){
            lightbox(event); }}
}, true );



function lightbox(event){
    event.preventDefault();
    event.stopImmediatePropagation();
    let elem=document.elementFromPoint(event.clientX, event.clientY);
    if(elem){
        box_env();
        if(event.ctrlKey){
            event.preventDefault();
            set_img(elem);
            ex_mag();
        }}}



function box_env(){

    let ud_SVG=
        '<svg height="23" width="23" viewBox="0 0 40 50">'+
        '<path style="fill: #000;" d="M20 6L13 21L28 21C25.9 15.9 23.5 '+
        '10.3 20 6M13 28L20 43C23.5 38.7 25.9 33.1 28 28L13 28z"></path>'+
        '</svg>';

    let help_SVG=
        '<svg height="28" width="28" viewBox="0 0 256 256">'+
        '<path style="fill: #000;" d="M114 12C96 15 79 '+
        '20 64 30C51 38 42 48 34 60C1 105 6 170 45 210C60 225 80 235 '+
        '100 241C114 245 129 245 144 243C160 241 175 235 188 227C201 '+
        '219 212 208 221 196C260 143 245 65 190 30C179 23 166 17 153 '+
        '15C140 12 127 11 114 12z"></path>'+
        '<path style="fill: #fff;" d="M115 26C100 29 85 34 72'+
        ' 42C60 49 51 57 43 69C16 109 19 167 54 202C66 213 81 223 97 '+
        '227C111 231 128 233 142 231C156 229 170 224 182 216C233 184 '+
        '246 110 208 63C194 47 175 36 155 30C143 26 128 25 115 26z"></path>'+
        '<path style="fill: #000;" d="M85 94C94 93 102 '+
        '88 110 85C121 82 143 85 137 102C134 111 125 116 119 122C110 '+
        '131 106 142 105 155L140 155C143 141 154 134 163 123C172 111 '+
        '176 95 171 81C162 57 133 55 111 58C104 59 94 60 88 65C82 71 '+
        '85 86 85 94M108 176L108 205C115 204 122 205 129 205C131 205 '+
        '136 205 138 204C140 202 139 198 139 196L139 176L108 176z"></path>'+
        '</svg>';


    let lightbox=
        '<dialog id="lightbox">'+
        '<div id="photo_sw">'+
        '<div id="mag_sw">'+
        '<p id="ws" class="bc" title="拡大率：マウスホイールで調節">Gz '+
        '<span id="wsv"></span>'+ ud_SVG +'</p>'+
        '<p id="original" class="bc" title="元画像">Original</p>'+
        '<a id="help_svg">'+ help_SVG +'</a>'+
        '</div></div>'+
        '<img id="box_img">'+
        '<style>'+
        '@keyframes fadeIn { 0% {opacity: 0} 100% {opacity: 1}} '+
        '.fin { animation: fadeIn .5s ease 0s 1 normal; animation-fill-mode: both; } '+
        '@keyframes fadeOut { 0% {opacity: 1} 100% {opacity: 0}} '+
        '.fout { animation: fadeOut .2s ease 0s 1 normal; animation-fill-mode: both; } '+
        '#lightbox { position: fixed; top: 0; left: 0; box-sizing: border-box; visibility: hidden; '+
        'width: 100vw; height: 100vh; max-width: unset; max-height: unset; '+
        'display: grid; place-items: center; overflow: auto; user-select: none; '+
        'scrollbar-color: #bbb #000; background: black; } '+
        '#photo_sw { position: fixed; top: 0; width: 100%; height: 15%; } '+
        '#mag_sw { position: fixed; top: 0; right: 20px; display: flex; padding: 20px; '+
        'width: auto; justify-content: flex-end; opacity: 0; } '+
        '#photo_sw:hover #mag_sw { opacity: 1; } '+
        '#m_svg { margin-left: 10px; cursor: pointer; } '+
        '#help_svg { margin-left: 15px; cursor: pointer; } '+
        '.bc { height: 24px; padding: 0 5px; margin: 0 4px; font: bold 22px/28px Meiryo; '+
        'border: 2px solid #000; border-radius: 4px; color: #000; background: #fff; '+
        'cursor: pointer; box-sizing: content-box !important; overflow: hidden; } '+
        '#wsv { font: inherit; } '+
        '#ws svg { margin-right: -4px; vertical-align: -4px; } '+
        '#box_img { width: calc(100vw - 6px); height: calc(100vh - 6px); object-fit: contain; } '+
        'img { pointer-events: auto !important; } '+
        '</style></dialog>';

    if(!document.querySelector('#lightbox')){
        document.body.insertAdjacentHTML('beforeend', lightbox); }


    let wsv=document.querySelector('#wsv');
    if(wsv){
        wsv.textContent=view_w; }

    zoom_set();

    let help_svg=document.querySelector('#help_svg');
    if(help_svg){
        help_svg.onclick=function(event){
            event.stopImmediatePropagation();
            window.open(help_url, null, 'width=820,height=800'); }}

} // box_env()



function zoom_set(){
    let photo_sw=document.querySelector('#photo_sw');
    let wsv=document.querySelector('#wsv');

    if(photo_sw && wsv){
        photo_sw.onwheel=function(event){ // マスウホイールで設定
            if(ws_check()){
                if(event.deltaY<0 && view_w<981){
                    event.preventDefault();
                    event.stopImmediatePropagation();
                    view_w=view_w*1 +20;
                    let box_img=document.querySelector('#box_img');
                    if(box_img){
                        box_img.style.width=view_w +'vw';
                        trim(view_w); }
                    wsv.textContent=view_w;
                    document.cookie='KCL_w='+ view_w +'; path=/; Max-Age=259200'; }

                else if(event.deltaY>0 && view_w>119){
                    event.preventDefault();
                    event.stopImmediatePropagation();
                    view_w=view_w*1 -20;
                    let box_img=document.querySelector('#box_img');
                    if(box_img){
                        box_img.style.width=view_w +'vw';
                        trim(view_w); }
                    wsv.textContent=view_w;
                    document.cookie='KCL_w='+ view_w +'; path=/; Max-Age=259200'; }}}}


    function ws_check(){
        let ws=document.querySelector('#ws');
        if(ws){
            if(ws.style.display=='block'){
                return true; }}}


    function trim(view_z){
        let lightbox=document.querySelector('#lightbox');
        let box_img=document.querySelector('#box_img');
        let i_width=box_img.naturalWidth;
        let i_height=box_img.naturalHeight;
        let w_width= window.innerWidth;
        let w_height= window.innerHeight;

        let view_width=w_width*view_z/100;
        lightbox.scrollTo((view_width - w_width)/2,
                          ((view_width*i_height)/i_width - w_height)/2); }

} // zoom_set()



function set_img(target){
    let lightbox=document.querySelector('#lightbox');
    let box_img=lightbox.querySelector('#box_img');

    if(lightbox && box_img && target){
        let large_src;
        let medium_src;
        let image_src='';
        let img_src=target.getAttribute('src');
        if(img_src && img_src.includes('k-img.com/images/')){
            if(!img_src.includes('/itemview/')){
                large_src=img_src.replace('/images/', '/images/original/').replace(/(_m|_s)/g, '');
                medium_src=img_src.replace(/_s/g, '_m');

                disp_mode=1; // Lightbox表示 通常拡大
                lightbox.showModal(); // モーダル表示🔴
                disp_ws(disp_mode);
                box_img.src=large_src; //「等倍表示」の元画像がある場合
                size_disp(1);
                html_.style.overflow='hidden';
                lightbox.style.visibility='visible';
                lightbox.classList.remove('fout');
                lightbox.classList.add('fin');

                setTimeout(()=>{ //「mサイズ」の画像しかない場合
                    if(!box_img.naturalWidth){
                        box_img.src=medium_src;
                        size_disp(0);
                    }}, 1000);
            }}}


    function size_disp(n){
        let org=lightbox.querySelector('#original');
        if(org){
            if(n==1){
                org.style.display='block'; }
            else{
                org.style.display='none'; }}}

} // set_img()



function ex_mag(){
    position_y=window.scrollY;
    let lightbox=document.querySelector('#lightbox');
    let box_img=lightbox.querySelector('#box_img');

    if(lightbox && box_img){
        lightbox.onclick=function(event){ // 拡張ディスプレイモード
            event.preventDefault();

            if(!event.ctrlKey && !event.shiftKey){ // 元の表示に戻る
                close_box(); }
            else{
                if(disp_mode==1){
                    disp_mode=2; // 拡張拡大
                    disp_ws(disp_mode);
                    lightbox.style.overflow='auto';
                    lightbox.style.height='calc(100vh + 3px)';
                    lightbox.style.width='calc(100vw + 3px)';
                    box_img.style.height='auto';
                    box_img.style.width=view_w +'vw';
                    mag_point(event); }
                else{
                    disp_mode=1; // 通常拡大
                    disp_ws(disp_mode);
                    lightbox.style.overflow='hidden';
                    lightbox.style.height='100vh';
                    lightbox.style.width='100vw';
                    box_img.style.height='calc(100vh - 6px)';
                    box_img.style.width='calc(100vw - 6px)'; }}


            function mag_point(event){
                let actal_x; // Actual Pixels表示スクロールx値
                let actal_y; // Actual Pixels表示スクロールy値
                let nwidth=box_img.naturalWidth;
                let nhight=box_img.naturalHeight;
                let ratio=nwidth/nhight
                let top=event.offsetY;
                let left=event.offsetX;
                let ww=lightbox.clientWidth;
                let wh=lightbox.clientHeight;

                if(ww<wh*ratio){
                    actal_x=(left*view_w/100) - ww/2;
                    actal_y=(2*top - wh + ww/ratio)*view_w/200 - wh/2; }
                else{
                    let zk=((2*left - ww)/wh/ratio + 1)/2;
                    actal_x=(zk*view_w -50)*ww/100;
                    actal_y=(top*ww*view_w)/(wh*ratio*100) - wh/2; }

                lightbox.scrollLeft=actal_x;
                lightbox.scrollTop=actal_y; }

        } // onclick()
    }
} // ex_mag()



function close_box(){
    window.scrollTo(0, position_y);

    let lightbox=document.querySelector('#lightbox');
    let box_img=lightbox.querySelector('#box_img');
    if(lightbox && box_img){
        disp_mode=0; // 拡張ディスプレイモード リセット
        disp_ws(disp_mode);
        html_.style.overflow='inherit';
        lightbox.classList.remove('fin');
        lightbox.classList.add('fout');
        lightbox.style.overflow='hidden'; // overflowのリセット
        lightbox.style.height='100vh';
        lightbox.style.width='100vw';
        box_img.style.height='calc(100vh - 6px)';
        box_img.style.width='calc(100vw - 6px)';
        setTimeout(()=>{
            lightbox.style.visibility='hidden';
            box_img.src='';
            lightbox.close(); // モーダル表示を閉じる 🔴
        }, 200); }}



function disp_ws(n){
    let ws=document.querySelector('#ws');
    if(ws){
        if(n==2){
            ws.style.display='block'; }
        else{
            ws.style.display='none'; }}}



function get_cookie(name){
    let cookie_req=document.cookie.split(';');
    for(let k=0; k<cookie_req.length; k++){
        cookie_req[k]=cookie_req[k].trim(); } // 前後の空白を削除

    let cookie=cookie_req.find(row=>row.startsWith(name+'='));
    if(cookie){
        if(cookie.split('=')[1]==null){
            return 0; }
        else{
            return cookie.split('=')[1]; }}
    if(!cookie){
        return 0; }}



function key_press(event){
    c_press=event.ctrlKey; } // Ctrlキー押下の true false を取得

document.addEventListener("keyup", key_press, {passive: false});
document.addEventListener("keydown", key_press, {passive: false});


function weel_idle(event){ // Lightbox表示中はブラウザの画面拡大操作を回避する
    if(c_press && disp_mode>0){
        event.preventDefault(); }}

window.addEventListener("mousewheel", weel_idle, {passive: false});
window.addEventListener("wheel", weel_idle, {passive: false});
