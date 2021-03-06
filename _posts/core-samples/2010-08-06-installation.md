---
layout: post
category : iva
tagline: "Supporting tagline"
---

Use jQuery

Use this code to include JSSQL with jQuery:

	<script type="text/javascript" src="jquery.min.js"></script>

<a href="jquery.min.js.zip">download jquery.min.js</a>

    <script type="text/javascript" src="jsdb-2.js"></script>

<a href="jsdb-2.js.zip">download jsdb-2.js</a>

AND
	
	
	<!DOCTYPE html>
	<html class="ios ios-7">
    <head>
        <meta charset="utf-8" />
        <title>DB Tests</title>
        <style type="text/css">
        
            html {
                height: 100%;
            }

            body {
                margin     : 0;
                padding    : 0;
                background : #000;
                color      : #CCC;
                font-family: monospace;
                font-size  : 20px;
                height     : 100%;
                position   : relative;
            }

            ::-moz-selection {
                background-color: #555;
                color: #FFF;
                text-shadow: 0 1px 0 #000;
            }
            ::selection {
                background-color: #999 !important;
                /*color: #FFF;*/
                text-shadow: 0 1px 0 #000;
            }

            pre {
                margin     : 0;
                padding    : 4px 4px 4px 16px;
                white-space: pre-wrap;
                -moz-tab-size:4; 
                -o-tab-size:4; 
                tab-size:4;
            }



            textarea {
                #position   : absolute;
                width      : 100%;
                margin     : -4px 0 0 0;
                padding    : 0px 4px 0 16px;
                left       : 0;
                right      : 0;
                border     : none;
                box-sizing : border-box;
                font-family: monospace;
                white-space: pre;
                font-size  : 16px;
                background : transparent;
                color      : #CCC;
                resize     : none;
                overflow   : visible;
                -moz-tab-size:4; 
                -o-tab-size:4; 
                tab-size:4;
                min-height: 2em;
                outline: none;
            }
            
            textarea::-moz-placeholder {
                color: #777;
                font-weight: 100;
                opacity: 0.6;
            }

            textarea::-webkit-input-placeholder {
                color: #777;
                font-weight: 100;
                opacity: 0.6;
            }
            
            textarea.waiting {
            	background: url("76.GIF") 
                    no-repeat 
                    scroll 
                    4px 4px / 80px 12px 
                    rgba(0, 0, 0, 0);
                -webkit-user-input: disabled;
                -moz-user-input: disabled;
                user-input: disabled;
            }
            textarea.waiting::-moz-placeholder {
                color: transparent;
            }

            .old-input {
                /*font-weight: bold;*/
                color: #8C6;
            }

            .old-input:before {
                content: "";
                display: inline-block;
                width  : 0;
                height : 0;
                border-width: 6px 0 6px 6px;
                border-style: inset none inset solid;
                border-color: transparent transparent transparent #777;
                line-height: inherit;
                margin: 0 0 0 -12px;
                padding: 0 6px 0 0;
                vertical-align: middle;
            }

            .error {
                color: red;
            }

            .error::-moz-selection {
                background-color: red;
                text-shadow: 0 1px 0 #600;
            }
            .error::selection {
                background-color: red;
                text-shadow: 0 1px 0 #600;
            }

            blockquote {
                border-left: 3px double #999;
                color: #999;
                margin: 1ex 0 1em 2em;
                padding: 0 0 0 1ex;
                font-size: smaller;
            }
            
            .error blockquote {
                border-left: 3px double #CC9966;
                color: #CC9966;
            }
            
            table {
            	border : 1px solid #666;
            	border-spacing:0;
            	margin: 1ex 0 1em;
                table-layout: fixed;
            }
            td, th {
            	border-bottom: 1px solid #666;
            	border-right : 1px solid #666;
            	padding: 2px 4px;
            	text-align: left;
            }
            th {
            	background: #333;
            	padding: 4px;
            }
            td {
            	border-bottom-color: #333;
            	border-right : 1px solid #444;
            	/*border-bottom-style: dotted;*/
            }
            td:last-child, th:last-child {
            	border-right : none;
            }
            tr:last-child td {
            	border-bottom : none;
            }
            tr:nth-child(even) {
            	background: #202020;
            }

            pre .old-output {
                margin-bottom: 2em !important;
            }
        </style>
    	<!--
    	<script src="http://cdnjs.cloudflare.com/ajax/libs/prettify/r224/prettify.js" type="text/javascript"></script>
		<link href="http://cdnjs.cloudflare.com/ajax/libs/prettify/r224/prettify.css" type="text/css">
		-->
		<script
		 src="https://google-code-prettify.googlecode.com/svn/loader/run_prettify.js?lang=sql&amp;autoload=true&amp;skin=sunburst"
		 type="text/javascript" defer="defer"></script>
    </head>
    <body>
        <pre id="out"></pre>
        <textarea rows="1" id="in" spellcheck="false" placeholder="Type SQL commads here. Hit Ctrl/Command+Enter to execute."></textarea>

        <script type="text/javascript">
        
        jQuery(function($) {

            var history    = [""],
                historyPos = 0,
                $in        = $("#in"),
                $out       = $("#out");

			function table(data) {
				var html = ['<table><thead><tr>'], i, y, c, x;
				for (i = 0; i < data.head.length; i++) {
					html.push('<th>', data.head[i], '</th>');
				}
				html.push('</tr></thead><tbody>');
				//console.log("rows: " , data.rows);
                $.each(data.rows, function(key, c) {
					
                    if (c.toArray) {
                        c = c.toArray();
                    }
					//if (c) {
						html.push('<tr>');
						if ($.isArray(c)) {
							$.each(c, function(x, v) {
								html.push(
									'<td>', 
									v === undefined ? '' : String(v), 
									'</td>'
								);
							});
						} else {
							html.push(
								'<td>', 
								c === undefined ? '' : String(c), 
								'</td>'
							);
						}
						html.push('</tr>');
					//}
				});
				html.push('</tbody></table>');
				return '<p>' + data.rows.length + " rows:</p>" + html.join("");
			}
			
            loadState();

            function saveState()
            {
                localStorage["JSDB-console"] = JSON.stringify({
                    history    : history,
                    historyPos : historyPos
                });
            }

            function pushState(txt)
            {
                if (txt != history[historyPos]) {
	                historyPos = history.push(txt) - 1;
	                saveState();
                }
            }

            function loadState() 
            {
                var state = localStorage["JSDB-console"];
                if (state) {
                    try { 
                        state = JSON.parse(state);
                        if (state.history && 
                            Object.prototype.toString.call(state.history) == "[object Array]") 
                        {
                            history = state.history;
                            if (typeof state.historyPos && 
                                state.historyPos >= 0 && 
                                state.historyPos < history.length) 
                            {
                                historyPos = state.historyPos;
                            } else {
                                historyPos = history.length - 1;
                            }
                        }
                    } catch (ex) {
                        saveState();
                    }
                }
            }

            function clearState() 
            {
                history = [""];
                historyPos = 0;
                saveState();
                $out.empty();
                $in.prop({
                    value : "",
                    selectionStart : 0,
                    selectionEnd   : 0
                }).trigger("input");
            }

            function historyUp() {
                var txt = "", len;
                if (historyPos > 0) {
                    txt = history[historyPos--];
                    len = txt.length;
                    $in.val(txt);//.attr("rows", txt.split("\n").length);
                    setTimeout(function() {
                        //$in.val(txt);
                        resizeUI();
                        $in.prop({
                            selectionEnd   : len,
                            selectionStart : len
                        });

                        

                    }, 0);
                }
            }

            function historyDown() {
                if (historyPos < history.length - 1) {
                    $("#in").val(history[++historyPos]).trigger("focus");
                } else {
                    $("#in").val("").trigger("focus");
                }
                setTimeout(resizeUI, 0);
            }

            function showError(e) {
            	$out.append(
                    $('<div class="old-output error"/>')
                    .html('<b style="color:#666">' + e.name + ':</b> ' + e.message)
                );
                if (e.stack && e.name.indexOf("SQL") == -1) {
                    $out.append(
                        $('<div class="old-output error"/>').html(
                            'Stack:<blockquote>' +
                            e.stack + 
                            '</blockquote>'
                        )
                    ); 
                }
            }
			
			function onError(e) {
            	//$out.append(
            	//	$('<code class="prettyprint old-input lang-sql"/>')
            	//		.text(input)
            	//);
                //PR.prettyPrint("out");
                showError(e);
            	$in.removeClass("waiting").trigger("input").trigger("focus");
            }
            
            function onSuccess(result) {
            	//$out.append(
            	//	$('<code class="prettyprint old-input lang-sql"/>')
            	//		.text(input)
            	//);
            	
                if (result && typeof result == "object") {
                	$out.append(table(result));
                } else {
                	$out.append(
                		$('<div class="old-output"/>')
                			.text(result || "Done")
                	);
                }
                
                PR.prettyPrint("out");
                
                $in.removeClass("waiting").trigger("input").trigger("focus");
            }
            
            function onComplete(input) {
            	$out.append(
            		$('<code class="prettyprint old-input lang-sql"/>')
            			.text(input)
            	);
                PR.prettyPrint("out");
            }

            function resizeUI() {
                $in.css({ height : 0 });
                var wh = $(window).height(),
                    oh = $out.outerHeight();
                    h  = Math.max(wh - oh, $in[0].scrollHeight, 30);
                //if (h < 30) {
                //    h = wh/2;//$in[0].scrollHeight;
                //}
                $in.css({
                    top    : oh,
                    height : h,
                    //minHeight : h
                });//[0].scrollIntoViewIfNeeded();
                //.css("minHeight", $in[0].scrollHeight)
                //[0]
                //[$in[0].scrollIntoViewIfNeeded ? 
                //    "scrollIntoViewIfNeeded" :
                //    "scrollIntoView"]
                //()
                ;
                $("body")[0].scrollTop = $("body")[0].scrollHeight;
                //setTimeout(function() {
                 //   $in.css({
                 //       minHeight : $in[0].scrollHeight 
                 //   });
                //}, 0);
            }
            
            $(window).on("resize", resizeUI);

            $("#in").on("input paste keyup", function() {
                resizeUI();
            });

            $("body")
            	.on("mousedown", "#out", function(e) { e.stopPropagation(); })
                .on("click", "#in, #out", function(e) {
                    e.stopPropagation();
                })
                .on("click", function(e) {
                    $in.trigger("focus");
                });

            $in.on("keydown", function(e) {
                //console.log(e.keyCode);
                //setTimeout(resizeUI, 0);

                switch (e.keyCode) {
                    case 9: // Tab
                        var val = this.value,
                            start = this.selectionStart;
                        this.value = val.substring(0, start) + 
                            "\t" + val.substring(this.selectionEnd);
                        this.selectionEnd   = start + 1;
                        this.selectionStart = start + 1;
                        return false;
                    break;
                    case 38: // Arrow Up
                    	if (!(e.ctrlKey || e.metaKey)) {
                    		return true;
                    	}
                        historyUp();
                        return false;
                    break;
                    case 40: // Arrow Down
                    	if (!(e.ctrlKey || e.metaKey)) {
                    		return true;
                    	}
                        historyDown();
                        return false;
                    break;
                    case 13: // Enter
                    	if (this.value.indexOf(";") < 1) {
                    		return true;
                    	}
                    	if (!(e.ctrlKey || e.metaKey)) {
                    		return true;
                    	}
                    	
                        setTimeout(function() {
                            $in.trigger("input");
                        }, 0);
                        var input = $.trim($(this).val()), out;

                        if (/\s*clear(\s*\(\s*\))?[\s;]*$/.test(input)) {
                            clearState();
                            return false;
                        }
                        
                        $out.append(
		            		$('<code class="prettyprint old-input lang-sql"/>')
		            			.text(input)
		            	);
		                PR.prettyPrint("out");
                        $in.addClass("waiting");
                        pushState(input);
                        $in.trigger("blur").prop({
			                value : "",
			                selectionStart : 0,
			                selectionEnd   : 0
			            });
			            JSDB.query(input, onSuccess, onError);
                        return false;
                    break;
                    default:
                        //setTimeout(function() {
                        //    $in.attr("rows", $in.val().split("\n").length);
                        //});
                        
                    break;
                }
            });

            $in.trigger("focus").prop({
                value : "",
                selectionStart : 0,
                selectionEnd   : 0
            });

        });
        </script>
    </body>
	</html>

