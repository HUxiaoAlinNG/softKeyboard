#在线网站：https://huxiaoalinng.github.io/softKeyboard/
html文件           :引用jquery-1.8.2.min.js/vk_loader.js

vk_loader.js       :引用e.js/scriptqueue.js/virtualkeyboard.js/layouts.js

e.js               :定义各种函数

scriptqueue.js     :遍历script函数

virtualkeyboard.js :主函数，若更改js文件至其他文件，需更改154行代码 return l + "/js/" + io

layouts.js         :引用CN.js/chinese-pynsimpl.js/us.js

us.js              :英文模式下相关按键（除功能键）的字符

CN.js/chinese-pynsimpl.js:中文模式下相关按键（除功能键）的字符以及汉字库




引用键盘步骤：

   1）在html文件只需要引用vk_loader.js和jquery-1.8.2.min.js.
   如：<script type="text/javascript" src="js/DataCheck2.js"></script>
	 <script type="text/javascript" src="js/vk_loader.js" ></script>

   2）html页面加入“<div id="softkey"></div>” （键盘显示模块）

   3）input标签（或其他标签）下加ID，加onfocus和onblur事件。
   如：<input type="text" id="keyboardID" onfocus='test();' onblur="VirtualKeyboard.toggle('keyboardID','softkey');" />

   4）定义test函数
   如：function test(){
            VirtualKeyb	oard.toggle('keyboardID', 'softkey');
            $("#kb_langselector,#kb_mappingselector,#copyrights").css("display", "none");
            $("#virtualKeyboard").css({"margin-top":"409px","margin-left":"365px"});    //键盘位置
	    $("#VirtualKeyboardIME").css("margin-top":"5px","margin-left":"-500px");    //显示字体框位置
        }

