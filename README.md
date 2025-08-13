<!doctype html>
<html style="font-size: 62px;">
<head>
	<title>加拿大28</title>
	<meta name="viewport" content="width=device-width,initial-scale=1.0,maximum-scale=1.0,user-scalable=no">
	<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
	<script src='/Public/Common/js/socket.io.js'></script>
	<script type="text/javascript" src="http://apps.bdimg.com/libs/jquery/2.1.4/jquery.min.js"></script>
	<script type="text/javascript" src="__PUBLIC__/Home/new/css/js/artDialog.js"></script>
	<script type="text/javascript" src="__PUBLIC__/Home/new/css/js/page.js"></script>
	<script src="__PUBLIC__/layer/layer.js"></script>
	<link rel="stylesheet" href="__PUBLIC__/Home/new/css/index.css" />
	<link rel="stylesheet" href="__PUBLIC__/Home/new/css/page.css" />
	<link rel="stylesheet" href="__PUBLIC__/Home/new/css/gamepage.css" />
	<link rel="stylesheet" href="__PUBLIC__/Home/new/css/gamere.css" />
	<link href="__PUBLIC__/css/floatcss/index.css" rel="stylesheet" type="text/css">
	<style>
		body {
			position: relative;
			font-size: 14px;
			margin: 0;
			padding: 0;
			height: 100vh;
			display: flex;
			flex-direction: column;
		}
		.openmo {
			position: relative;
			z-index: 9;
		}
		.maskContent {
			position: absolute;
			top: 0;
			bottom: 0;
			left: 0;
			right: 0;
			background: rgb(0,0,0,0.3);
			z-index: 1;
			height: 800px;
			display: none;
		}
		.maskBody {
			position: fixed;
			top: 0;
			left: 0;
			right: 0;
			bottom: 90vw;
			z-index: 10;
		}
		.kefu-icon {
			float: right;
			margin-right: 10px;
			margin-top: 12px;
		}
		.kefu-icon img {
			width: 30px;
			height: 30px;
			vertical-align: middle;
		}
		.scroll-to-bottom {
			position: fixed;
			right: 10px;
			bottom: 100px;
			width: 40px;
			height: 40px;
			cursor: pointer;
			z-index: 11;
			transition: bottom 0.3s ease;
		}
		.scroll-to-bottom img {
			width: 100%;
			height: 100%;
		}
		.main .betup {
			font-size: 16px;
		}
		.main .betup .uname, .main .betup .ubet, .main .betup .notice, .main .betup .bettime {
			font-size: 16px !important;
		}
		header {
			height: 50px;
		}
		.main {
			flex: 1;
			overflow-y: auto;
		}
		.chat_box {
			flex-shrink: 0;
		}
		.digital {
			position: fixed;
			bottom: -100vw;
			left: 0;
			width: 100%;
			z-index: 12;
			transition: bottom 0.3s ease;
		}
		.digital.active {
			bottom: 0;
		}
		.digital * {
			font-weight: bold !important;
		}
		.digital .title, .digital .libtn p, .digital .bluebg {
			font-weight: bold;
		}
		/* 倍数文本使用灰色 */
		.digital .swipe-item div:nth-child(2),
		.digital .libtn p:nth-child(2) {
			color: #808080; /* 灰色 */
		}
		/* 0-9 数字按钮字体增大 3px */
		.digital .bluebg {
			font-size: 18px; /* 默认 15px + 3px */
		}
		/* 调整特定区域字体大小 */
		header h2, .gmfl p, .open div, .chat_box button, .bm-box-form input {
			font-size: 15px;
		}
		* 提示框样式，从 new.html 学习 */
		.alert {
			display: none;
			position: fixed;
			top: 50%;
			left: 70%;
			transform: translate(-50%, -50%);
			background-color: rgba(128, 128, 128, 0.9);
			color: #fff;
			padding: 10px 20px;
			border-radius: 5px;
			z-index: 1000;
			font-size: 16px;
			text-align: center;
		}
	</style>
</head>
<body onLoad="connect(15535);">
	<header style="background: #ffffff">
		<a onClick="history.go(-1)"><i class="ico02 back fl" style=" transform: rotate(90deg);"></i></a>
		<h2>加拿大28</h2>
		<i class="ico null"></i>
		<i class="ico plus qx45 fr"></i>
		<a href="/Home/User/index_1.html" class="kefu-icon">
			<img src="/../img/kefutx.png" alt="客服">
		</a>
	</header>
	<div class="headblank"></div>
	<div class="maskBody" style="display: none"></div>
	<div class="gmfix">
		<div id="01" class="gmfl01">
			<div class="gmfl">
				<p class="line1">第 <i><b></b></i> 期开奖</p>
				<p class="line2">0</p>
			</div>
			<script type="text/javascript">
				$(function () {
					setInterval(function () {
						$("#gmfr").load(location.href + " #gmfr");
					}, 2000); //8秒自动刷新
				})
			</script>
			<div class="gmfl">
				<p class="line3"><i style="color:#000">余额</i> <span class="yeup"></span></p>
				<div id="gmfr">
					<p class="line4" align="right">{$userinfo.points} </p>
				</div>
			</div>
		</div>
		<div class="open" onClick="a1()">
			<input type="hidden" value="{$kjlist[0].game}" id="gameNub" />
			<div id="02" style="padding: 0.1rem 0.2rem;display: flex;">
				<div style="display: flex">
					<div style="width:27.5vw">第 <i>{$kjlist[0].periodnumber}</i> 期</div>
					<div style="width: 38vw">
						<span class="num">{$kjlist[0].numberOne}</span> +
						<span class="num">{$kjlist[0].numberTwo}</span> +
						<span class="num">{$kjlist[0].numberThree}</span> =
						<span class="num">{$kjlist[0].tema}</span>　
					</div>
				</div>
				<div style="margin-left: 12px;color: red">
					{$kjlist[0].tema_dx}{$kjlist[0].tema_ds} {$kjlist[0].lhb}　{$kjlist[0].q3}
					<li class="ico02 down fr"></li>
				</div>
			</div>
			<div id="o" style="position: relative;">
				<div class="maskContent"></div>
				<ul class="openmo" style="padding-left:0;">
					<volist name="kjlist" id="vo">
						<li style="padding: 0 0.2rem;display: flex;">
							<div style="display: flex">
								<div style="width:27.5vw">第 <i style="color:#3da1fe">{$vo.periodnumber}</i> 期</div>
								<div style="width: 38vw;display:flex;">
									<div style="width: 19vw">已开奖</div>
									<div style="width: 19vw">
										<span>{$vo.numberOne}</span>+<span class="">{$vo.numberTwo}</span>+<span class="">{$vo.numberThree}</span>=<span class="">{$vo.tema}</span>
									</div>
								</div>
							</div>
							<div style="margin-left: 16px">
								{$vo.tema_dx}{$vo.tema_ds} {$vo.lhb} {$vo.q3}
							</div>
						</li>
					</volist>
				</ul>
			</div>
		</div>
		<p><a id="aButton" href="JavaScript:void(0)" onclick="openDialog()" style="color:#fff;font-size:15px;font-weight:bolder;background-color:#3da1fe;padding:15px 15px 6px 15px;border-radius:7px;display:none;">本期下注:<label id="label">0</label></a> </p> <br>
	</div>
	<!--聊天开始-->
<div class="main">
<ul class="betup"><p class="gonggao"><marquee scrollAmount=4 width=95%>{:C('welcome')}</marquee></p>
<div id="03">  
<li class="notices"><center>仅显示前100条竞猜记录</center></li>
<volist name="msglist" id="vo">
	<if condition="$vo['type'] eq 'admin'">
		<p class="bettime">{$vo.time}</p>
		<li class="notice"><center>{$vo.content|htmlspecialchars_decode|stripcslashes}</center></li>
	</if>	
	<if condition="$vo['type'] eq 'system'">
		<p class="bettime">{$vo.time}</p>
		<li class="notice"><center>{$vo.content|htmlspecialchars_decode|stripcslashes}</center></li>
	</if>
	<if condition="$vo['type'] eq 'say'">
	<div>
		<div style="color: #A0A2A3;text-align: center;">
			{$vo.time}
		</div>
		<div>
			<div class="uhead"><img src="{$vo.head_img_url}" style= "pointer-events: none;">
			</div>
			<div style="margin-left:-3px" class="betinfo">
				<p class="uname">{$vo.from_client_name}　　</p>
				<!--修改-->
				<div class="ubet"><!-- 修改  -->
<!--					<div><span class='theterm'>第xxx期:</span> <span style="">合计：{$vo.countNum}</span></div>-->
					<div id="viewall" style="background: #fff;border-radius:3px;padding: 5px;position: relative;z-index: 0;">
						<p sytle="display:flex;"> {$vo.newmsg}</p>
					</div>
				</div>
			</div>
		</div>
	</div>
	</if>
	<if condition="$vo['type'] eq 'fk'">
		<li>
			<div>
				<div class="uhead"><img src="{$vo.head_img_url}" style= "pointer-events: none;">
				</div>
				<div style="margin-left:-3px" class="betinfo">
					<p class="uname" style="color:#FF0000">系统接单 (已认证)</p>
					<div class="ubet">
						<div id="viewall" style="background: #fff;border-radius:3px;padding: 5px;position: relative;z-index: 0;">
							{$vo.content}
						</div>
					</div>

				</div>
			</div>
		</li>
	</if>
</volist>
			</div>
		</ul>
		</ul>
		<div class="scroll-to-bottom">
			<img src="/../img/brush.png" alt="Scroll to bottom">
		</div>
	</div>
	<!--聊天结束-->
	<div class="chat_box" style="background-color: #FFFFFF">
		<div style="width: 99%;margin:0 auto;background-color: #FFFFFF">
			<div style="width: 13%;margin-right:2%;float: left;background-color: #FFFFFF">
				<button type="button" class="kuitoubtn" style="background-color: #10DC60;color: #ffffff;height: 35px;width:100%;border-radius: 4px;font-size:16px;border: 1px solid transparent">
					投注
				</button>
			</div>
			<div style="width: 55%;float: left;background-color: #FFFFFF">
				<input disabled="disabled" style="background: #F2F2F2; border: 1px solid transparent;height: 34px;width:100%;border-radius: 4px;margin-left: 0;font-size:14px" type="text" placeholder="当前禁止发言" id='touzhu1' value="" maxlength="10" />
			</div>
			<div style="float: left;background-color: #FFFFFF;width: 30%;text-align: center;">
				<a href="/Home/Run/record" style="">
					<img style="width: 29px;height: 29px;margin-top: 3px;" src="/addls.png" alt="">
				</a>
			</div>
		</div>
		<div class="digital hide">
			<div class="row firstrow">
				<input type="text" id="content" placeholder="注码在左,金额在右,请规范下注.如大100">
				<button id="clearall">清空</button>
			</div>
			<div class="row sencondrow">
				<div class="left-arrow arrow"><i class="iconfont"></i></div>
				<div class="right-arrow arrow"><i class="iconfont"></i></div>
				<div class="swipe-contaiber">
					<div class="swipe-box">
						<div class="swipe-item l1">
							<div class="title">0</div>
							<div>{:C('jnd28_tema_0')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">1</div>
							<div>{:C('jnd28_tema_1')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">2</div>
							<div>{:C('jnd28_tema_2')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">3</div>
							<div>{:C('jnd28_tema_3')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">4</div>
							<div>{:C('jnd28_tema_4')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">5</div>
							<div>{:C('jnd28_tema_5')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">6</div>
							<div>{:C('jnd28_tema_6')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">7</div>
							<div>{:C('jnd28_tema_7')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">8</div>
							<div>{:C('jnd28_tema_8')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">9</div>
							<div>{:C('jnd28_tema_9')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">10</div>
							<div>{:C('jnd28_tema_10')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">11</div>
							<div>{:C('jnd28_tema_11')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">12</div>
							<div>{:C('jnd28_tema_12')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">13</div>
							<div>{:C('jnd28_tema_13')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">14</div>
							<div>{:C('jnd28_tema_13')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">15</div>
							<div>{:C('jnd28_tema_12')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">16</div>
							<div>{:C('jnd28_tema_11')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">17</div>
							<div>{:C('jnd28_tema_10')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">18</div>
							<div>{:C('jnd28_tema_9')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">19</div>
							<div>{:C('jnd28_tema_8')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">20</div>
							<div>{:C('jnd28_tema_7')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">21</div>
							<div>{:C('jnd28_tema_6')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">22</div>
							<div>{:C('jnd28_tema_5')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">23</div>
							<div>{:C('jnd28_tema_4')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">24</div>
							<div>{:C('jnd28_tema_3')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">25</div>
							<div>{:C('jnd28_tema_2')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">26</div>
							<div>{:C('jnd28_tema_1')}倍</div>
						</div>
						<div class="swipe-item l1">
							<div class="title">27</div>
							<div>{:C('jnd28_tema_0')}倍</div>
						</div>
					</div>
				</div>
			</div>
			<div class="row cliprow">
				<div class="libtn blueline">数据</div>			
				<div class="libtn blueline l2">
					<p>对子</p>
					<p>{:C('jnd28_bds_3')}倍</p>
				</div>
				<div class="libtn blueline l2">
					<p>顺子</p>
					<p>{:C('jnd28_bds_2')}倍</p>
				</div>
				<div class="libtn blueline l2">
					<p>豹子</p>
					<p>{:C('jnd28_bds_1')}倍</p>
				</div>
				<div class="libtn blueline" id="backstep"><i class="iconfont" style="font-size: 30px"></i></div>
			</div>
			<div class="row cliprow">
				<div class="libtn blueline l2">
					<p>大</p>
					<p>{:C('jnd28_dxds')}倍</p>
				</div>
				<div class="libtn bluebg">1</div>
				<div class="libtn bluebg">2</div>
				<div class="libtn bluebg">3</div>
				<div class="libtn blueline l2">
					<p>大单</p>
					<p>{:C('jnd28_zuhe_1')}倍</p>
				</div>
			</div>
			<div class="row cliprow">
				<div class="libtn blueline l2">
					<p>小</p>
					<p>{:C('jnd28_dxds')}倍</p>
				</div>
				<div class="libtn bluebg">4</div>
				<div class="libtn bluebg">5</div>
				<div class="libtn bluebg">6</div>
				<div class="libtn blueline l2">
					<p>大双</p>
					<p>{:C('jnd28_zuhe_2')}倍</p>
				</div>
			</div>
			<div class="row cliprow">
				<div class="libtn blueline l2">
					<p>单</p>
					<p>{:C('jnd28_dxds')}倍</p>
				</div>
				<div class="libtn bluebg">7</div>
				<div class="libtn bluebg">8</div>
				<div class="libtn bluebg">9</div>
				<div class="libtn blueline l2">
					<p>小单</p>
					<p>{:C('jnd28_zuhe_2')}倍</p>
				</div>
			</div>
			<div class="row cliprow">
				<div class="libtn blueline l2">
					<p>双</p>
					<p>{:C('jnd28_dxds')}倍</p>
				</div>
				<div class="libtn blueline l2">
					<p>极大</p>
					<p>{:C('jnd28_jdx')}倍</p>
				</div>
				<div class="libtn bluebg">0</div>
				<div class="libtn blueline l2">
					<p>极小</p>
					<p>{:C('jnd28_jdx')}倍</p>
				</div>
				<div class="libtn blueline l2">
					<p>小双</p>
					<p>{:C('jnd28_zuhe_1')}倍</p>
				</div>
			</div>
			<div class="row cliprow">
				<div class="libtn blueline l2" id="canclebtn" style="color:#fe4543;">
					取消投注
				</div>
				<div class="libtn blueline l2">
					<p>龙</p>
					<p>{:C('jnd28_jdx')}倍</p>
				</div>
				<div class="libtn blueline l2">
					<p>虎</p>
					<p>{:C('jnd28_jdx')}倍</p>
				</div>
				<div class="libtn blueline l2">
					<p>豹</p>
					<p>{:C('jnd28_jdx')}倍</p>
				</div>
				<div class="libtn" id="yesbtn" style="background-color: #4a92f4;color: #fff;font-size: 15px;">确认下注</div>
			</div>
		</div>
	</div>
	<!-- 投注 -->
	<div class="bm-layer-wrapper"></div>
	<div class="bm-layer bet-box">
		<div class="swiper-tab-title">
			<ul>
				<li>大小</li>
				<li>数字</li>
				<li>对顺豹</li>
			</ul>
		</div>
		<div class="bm-layer-trigger">
			<div class="bm-layer-prev"></div>
			<div class="bm-layer-next"></div>
		</div>
		<div class="bm-layer-fixed">
			<div class="bm-box-form" style='padding: 0.5rem 0.1rem;background: #eee;'>
				<div class="box-touzhu">50</div>
				<div class="box-touzhu">100</div>
				<div class="box-touzhu">200</div>
				<div class="box-touzhu">500</div>
				<div class="box-touzhu">1000</div>
				<div class="box-touzhu">2000</div>
				<div class="box-touzhu">梭哈</div>
			</div>
			<div class="bm-box-form" style="background: #fff;margin:0;border-top: 1px solid #a5a5a5;height: 0.88rem;">
				<input style="border: 2px solid #a5a5a5;height: 34px;border-radius: 8px;" type="text" placeholder="请输入投注元宝" value="" maxlength="10" id="J_jine" />
				<button type="button" class="bm-btn" id="J_touzhu" style="background-color: #3da1fe;color: #FFFFFF;height: 32px;border-radius: 10px;">下注</button>
				<button type="button" class="bm-btn" id="reset" style="background-color: #3da1fe;color: #FFFFFF;height: 32px;border-radius: 10px;">重置</button>
			</div>
		</div>
		<div class="swiper-container">
			<div class="swiper-wrapper">
				<div class="swiper-slide bm-box">
					<div class="bm-box-title">大小单双</div>
					<div class="bm-box-info"></div>
					<div class="bm-box-list">
						<ul>
							<li><span>大</span><p>{:C('jnd28_dxds')}倍</p></li>
							<li><span>小</span><p>{:C('jnd28_dxds')}倍</p></li>
							<li><span>单</span><p>{:C('jnd28_dxds')}倍</p></li>
							<li><span>双</span><p>{:C('jnd28_dxds')}倍</p></li>
							<li><span>大单</span><p>{:C('jnd28_zuhe_1')}倍</p></li>
							<li><span>大双</span><p>{:C('jnd28_zuhe_2')}倍</p></li>
							<li><span>小单</span><p>{:C('jnd28_zuhe_2')}倍</p></li>
							<li><span>小双</span><p>{:C('jnd28_zuhe_1')}倍</p></li>
							<li><span>极大</span><p>{:C('jnd28_jdx')}倍</p></li>
							<li><span>极小</span><p>{:C('jnd28_jdx')}倍</p></li>
						</ul>
					</div>
				</div>
				<if condition="C('jnd28_xz_open')['tema'] eq '1'">
					<div class="swiper-slide bm-box bm-box-red">
						<div class="bm-box-title">数字</div>
						<div class="bm-box-info"></div>
						<div class="bm-box-list">
							<ul>
								<li><span>0</span><p>{:C('jnd28_tema_0')}倍</p></li>
								<li><span>1</span><p>{:C('jnd28_tema_1')}倍</p></li>
								<li><span>2</span><p>{:C('jnd28_tema_2')}倍</p></li>
								<li><span>3</span><p>{:C('jnd28_tema_3')}倍</p></li>
								<li><span>4</span><p>{:C('jnd28_tema_4')}倍</p></li>
								<li><span>5</span><p>{:C('jnd28_tema_5')}倍</p></li>
								<li><span>6</span><p>{:C('jnd28_tema_6')}倍</p></li>
								<li><span>7</span><p>{:C('jnd28_tema_7')}倍</p></li>
								<li><span>8</span><p>{:C('jnd28_tema_8')}倍</p></li>
								<li><span>9</span><p>{:C('jnd28_tema_9')}倍</p></li>
								<li><span>10</span><p>{:C('jnd28_tema_10')}倍</p></li>
								<li><span>11</span><p>{:C('jnd28_tema_11')}倍</p></li>
								<li><span>12</span><p>{:C('jnd28_tema_12')}倍</p></li>
								<li><span>13</span><p>{:C('jnd28_tema_13')}倍</p></li>
								<li><span>14</span><p>{:C('jnd28_tema_13')}倍</p></li>
								<li><span>15</span><p>{:C('jnd28_tema_12')}倍</p></li>
								<li><span>16</span><p>{:C('jnd28_tema_11')}倍</p></li>
								<li><span>17</span><p>{:C('jnd28_tema_10')}倍</p></li>
								<li><span>18</span><p>{:C('jnd28_tema_9')}倍</p></li>
								<li><span>19</span><p>{:C('jnd28_tema_8')}倍</p></li>
								<li><span>20</span><p>{:C('jnd28_tema_7')}倍</p></li>
								<li><span>21</span><p>{:C('jnd28_tema_6')}倍</p></li>
								<li><span>22</span><p>{:C('jnd28_tema_5')}倍</p></li>
								<li><span>23</span><p>{:C('jnd28_tema_4')}倍</p></li>
								<li><span>24</span><p>{:C('jnd28_tema_3')}倍</p></li>
								<li><span>25</span><p>{:C('jnd28_tema_2')}倍</p></li>
								<li><span>26</span><p>{:C('jnd28_tema_1')}倍</p></li>
								<li><span>27</span><p>{:C('jnd28_tema_0')}倍</p></li>
							</ul>
						</div>
					</div>
				</if>
				<if condition="C('jnd28_xz_open')['bds'] eq '1'">
					<div class="swiper-slide bm-box">
						<div class="bm-box-title">对顺豹</div>
						<div class="bm-box-info"></div>
						<div class="bm-box-list">
							<ul>
								<li><span>对子</span><p>{:C('jnd28_bds_3')}倍</p></li>
								<li><span>顺子</span><p>{:C('jnd28_bds_2')}倍</p></li>							
								<li><span>豹子</span><p>{:C('jnd28_bds_1')}倍</p></li>
							</ul>
						</div>
					</div>
				</if>
			</div>
		</div>
	</div>
	<script>
		$('.box-touzhu').click(function(){
			$('.box-touzhu').removeClass("box-touzhu_on");
			$(this).addClass('box-touzhu_on');
			$('#J_jine').val($(this).html());
		})
	</script>
	<script type="text/javascript">
		function tel(){
			document.getElementById("J_jine").focus()
		}
		var tmp_top;
		$('#J_jine').focus(function(){
			tmp_top = $('body').scrollTop();
			$("body").scrollTop( $('body').height() );
		}).blur(function(){
			$("body").scrollTop( tmp_top );
		})
		;(function(){
			$('.J_quxiao').click(function(){
				$('.bm-layer-wrapper').click();
				art.dialog({
					content: '确定要取消本期全部投注吗？',
					lock: 1,
					ok: function(){
						$.ajax({
							url:'qx.php?do=1',
							data: {},
							success: function(data){
								document.getElementById("alert1").innerHTML=data
								$(".alert1").show();
								setTimeout( "$('.alert1').fadeOut()" , 1000)
							}
						})
					},
					cancelVal: '关闭',
					cancel: function(){}
				});
				return !1;
			})
			var mySwiper;
			mySwiper = new Swiper('.swiper-container');
			$('.bm-layer-prev').on('click', function(e){
				mySwiper.swipePrev();
			})
			$('.bm-layer-next').on('click', function(e){
				mySwiper.swipeNext();
			})
			$('.swiper-tab-title li').on('click', function(e){
				$(this).addClass('actived').siblings().removeClass('actived');
				var i = $(this).index();
				mySwiper.swipeTo(i);
			});
			$('.bm-box-list li').click(function(){
				if($(this).hasClass('bm-box-list-current')) $(this).removeClass('bm-box-list-current');
				else $(this).addClass('bm-box-list-current')
			})
			$('#J_show').click(function(){
				$('.bm-layer-wrapper').show();
				$('.bm-layer').show();
			})
			$('.bm-layer-wrapper').click(function(){
				$('.bm-layer-wrapper').hide();
				$('.bm-layer').hide();
			})
			$('#reset').on('click', function(e){
				$('#J_jine').val('');
			});
			$('#J_touzhu').click(function(){
				if($(this).attr("disabled")) {
					document.getElementById("alert").innerHTML="已封盘,禁止投注";
					$(".alert").show();
					setTimeout( "$('.alert').fadeOut()" , 1000);
					return !1;
				}
				var balance = parseInt($('.line4').text()) || 0;
				if(!$('.line4').text() || balance < 10) {
					document.getElementById("alert").innerHTML="余额需要大于10元才能发言";
					$(".alert").show();
					setTimeout( "$('.alert').fadeOut()" , 1000);
					return !1;
				}
				var active = $('.swiper-slide-active');
				var lx = $('.bm-box-title', active).html();
				var lx1 = [];
				$('.bm-box-list-current', active).each(function(){
					let html = $(this).find('span').html()
					lx1.push( html );
				})
				var je = $('#J_jine').val();
				if( !je.length ){
					document.getElementById("alert").innerHTML="金额不能为空";
					$(".alert").show();
					setTimeout( "$('.alert').fadeOut()" , 1000)
					return !1;
				}
				if (lx1.length === 0) {
					document.getElementById("alert").innerHTML="投注类型不能为空";
					$(".alert").show();
					setTimeout( "$('.alert').fadeOut()" , 1000)
					return !1;
				}
				var leng=lx1.length;
				if(lx1.length==0){
					var price = parseInt(je.replace(/[^0-9]/ig,""));
					var text=je.split(price);
					text=text[0];
					if(text==""){
						document.getElementById("alert").innerHTML="投注类型不存在";
						$(".alert").show();
						setTimeout( "$('.alert').fadeOut()" , 1000)
						return !1;
					}else if(text=="大" || text=="小" || text=="单" || text=="双" || text=="大单" || text=="小单" || text=="大双" || text=="小双" || text=="极大" || text=="极小"|| text=="对子" || text=="顺子" || text=="豹子"){
						input = text+price;
						onSubmit(input,leng);
					}
				}else{
					var je = parseInt(je.replace(/[^0-9]/ig,""));
					$.each(lx1, (i, v) => {
						var lx1 = v
						var input = "";
						if(lx=='数字'){
							input = lx1+'点'+je;
						}else{
							input = lx1+je;
						}
						onSubmit(input,leng);
					})
				}
			})
		})();
		function xiazhu(){
			var je = $('#touzhu1').val();
			if( !je.length ){
				document.getElementById("alert").innerHTML="金额不能为空";
				$(".alert").show();
				setTimeout( "$('.alert').fadeOut()" , 1000)
				return !1;
			}
			var price = parseInt(je.replace(/[^0-9]/ig,""));
			var text=je.split(price);
			text=text[0];
			if(text==""){
				document.getElementById("alert").innerHTML="投注类型不存在";
				$(".alert").show();
				setTimeout( "$('.alert').fadeOut()" , 1000)
				return !1;
			}else if(text=="大" || text=="小" || text=="单" || text=="双" || text=="大单" || text=="小单" || text=="大双" || text=="小双" || text=="极大" || text=="极小" || text=="对子" || text=="顺子" || text=="豹子"){
				input = text+price;
				onSubmit(input,1);
			}
		}
	</script>
	<include file="Template/Home/Run/js/lot_im.html"/>
	<script>
		var count = 0;
		function countDown(){
			$.ajax({
				url:'/Home/Get/getjnd28',
				data: {},
				success: function(data){
					data = JSON.parse(data);
					$(".line1").html("第 <i><b>"+data.drawIssue+"</b></i> 期开奖");
					count = data.time;
					executeCountDown();
					setInterval(function() {
						executeCountDown();
					}, 1000);
				}
			})
		}
		function executeCountDown(){
			if(count <= 0){
				$(".line2").html("已封盘");
				$('#J_touzhu').attr("disabled", true);
				$("#J_touzhu").css("background-color", "#c7c7c7");
				$('.kuitoubtn').attr("disabled", true);
				$('.kuitoubtn').css("background-color", "#c7c7c7");
			}else{
				count = count - 1;
				var formattedTime = formatSeconds(count);
				$(".line2").html('<span style="color:#ff0000;">' + formattedTime + '</span> <span style="color:#0e9aef">后封盘</span>');
				$('#J_touzhu').attr("disabled", false);
				$("#J_touzhu").css("background-color", "#3da1fe");
				$('.kuitoubtn').attr("disabled", false);
				$('.kuitoubtn').css("background-color", "#10DC60");
			}
		}
		function formatSeconds(value) {
			var secondTime = parseInt(value);
			var minuteTime = 0;
			var hourTime = 0;
			if(secondTime > 60){
				minuteTime = parseInt(secondTime / 60);
				secondTime = parseInt(secondTime % 60);
				if(minuteTime > 60) {
					hourTime = parseInt(minuteTime / 60);
					minuteTime = parseInt(minuteTime % 60);
				}
			}
			var result = " " + parseInt(secondTime);
			if(secondTime<10){
				result = '0' + parseInt(secondTime)
			}else{
				result = " " + parseInt(secondTime);
			}
			if(minuteTime > 0) {
				if(minuteTime>10){
					result = "" + parseInt(minuteTime) + ":" + result;
				}else{
					result = "0" + parseInt(minuteTime) + ":" + result;
				}
			}else{
				result = '00' + ':' + result
			}
			if(hourTime > 0) {
				result = "" + parseInt(hourTime) + "小时" + result;
			}
			return result;
		}
		countDown();
	</script>
	<script>
		var len=0;
		var checkFl="";
		var isSHow = false;
		$(".kuitoubtn").click(function () {
			if ($(this).attr("disabled")) {
				layer.open({
					content: '已封盘,禁止投注',
					skin: 'msg',
					time: 2,
					style: 'text-align:center; font-size:16px; color:#fff; background-color:#ff0000; border-radius:5px;'
				});
				return false;
			}
			var balance = parseInt($('.line4').text()) || 0;
			if(!$('.line4').text() || balance < 10) {
				document.getElementById("alert").innerHTML="余额需要大于10元才能发言";
				$(".alert").show();
				setTimeout("$('.alert').fadeOut()", 1000);
				return !1;
			}
			$(".digital").removeClass("hide").css("bottom","-5px");
			len=Math.ceil((".swipe-item").length/1);
			$(".swipe-box").width(len*300+"vw");
			$('.maskBody').show();
		})
		$('.maskBody').click(function(){
			$(".digital").addClass("hide").css("bottom","-100vw");
			$('.maskBody').hide();
		})
		$("#canclebtn").click(function () {
			$(".digital").addClass("hide").css("bottom","-100vw");
			$('.maskBody').hide();
		})
		var countNum=0;
		var numLeft=0;
		var allNum=Math.ceil(28/6)-1;
		$(".left-arrow").click(function(){
			if(countNum>0){
				countNum=countNum-1;
			}
			numLeft=-78*countNum;
			$(".swipe-box").css("left",numLeft+"vw");
		})
		$(".right-arrow").click(function(){
			if(countNum<allNum){
				countNum=countNum+1;
			}
			numLeft=-78*countNum;
			$(".swipe-box").css("left",numLeft+"vw");
		})
		var ddClick=false;
		$("#yesbtn").click(function(){
			if(ddClick){return;}
			var val=$(".firstrow input").val(),type=[];
			$(".sencondrow .swipe-item.active").each(function(index,element){
				var text=$(this).find(".title").text();
				var row={text:text,fl:"l1"};
				type.push(row);
			})
			$(".blueline.active.l2").each(function(index,element){
				var text=$(this).find("p:first-child").text();
				var row={text:text,fl:"l2"};
				type.push(row);
			})
			$(".blueline.active.l3").each(function(index,element){
				var text=$(this).find("p:first-child").text();
				var row={text:text,fl:"l3"};
				type.push(row);
			})
			var je = $('#content').val();
			if( !je.length ){
				document.getElementById("alert").innerHTML="金额不能为空";
				$(".alert").show();
				setTimeout( "$('.alert').fadeOut()" , 1000);
				return !1;
			}
			var leng=type.length;
			if(type.length==0){
				var price = parseInt(je.replace(/[^0-9]/ig,""));
				var text=je.split(price);
				text=text[0];
				if(text==""){
					document.getElementById("alert").innerHTML="投注类型不存在";
					$(".alert").show();
					setTimeout( "$('.alert').fadeOut()" , 1000);
					return !1;
				}else if(text=="大" || text=="小" || text=="单" || text=="双" || text=="大单" || text=="小单" || text=="大双" || text=="小双" || text=="极大" || text=="极小" || text=="对子" || text=="顺子" || text=="豹子"){
					input = text+price;
					onSubmit(input,leng);
					ddClick=true;
				}
			}else{
				var strs= new Array();
				strs=je.split(" ");
				var res=curtail(strs);
				$.each(type, (i, v) => {
					if(res[i]==null || res[i]==undefined || res[i]==""){
						return;
					}else{
						var input_one_txt='';
						if(res[i].indexOf('点')==1){
							input_one_txt= res[i].substr(0,1);
							res[i]= res[i].substr(1);
						}
						if(res[i].indexOf('点')==2){
							input_one_txt= res[i].substr(0,2);
							res[i]= res[i].substr(2);
						}
						var je = parseInt(res[i].replace(/[^0-9]/ig,""));
						if(res[i].indexOf('点')<0){
							input_one_txt=res[i].replace(/\d/g,"");
						}
						var type = v;
						if(type.fl!='l2'){
							var type = v;
							if(type.fl=='l1'){
								var type = {text:input_one_txt,fl:"l1"};
							}
						}else{
							var type = {text:input_one_txt,fl:"l2"};
						}
						var input = "";
						if(type.fl=='l1'){
							input = type.text+'点'+je;
						}else{
							input = type.text+je;
						}
						onSubmit(input,leng);
						ddClick=true;
					}
				})
			}
			$(".firstrow input").val('');
			$('.digital').find('.active').removeClass('active');
			ddClick=false;
		})
		$(".blueline.l2").click(function(){
			checkFl="l2";
			var txt=$(".firstrow input").val();
			var text=$(this).children(":first").text();
			if(text !=""){
				text=" "+text;
			}
			txt+=text;
			$(".firstrow input").val(txt);
			$(this).toggleClass("active");
		})
		$(".blueline.l3").click(function(){
			checkFl="l3";
			$(this).toggleClass("active");
		})
		$(".sencondrow .swipe-item.l1").click(function(){
			checkFl="l1";
			var txt=$(".firstrow input").val();
			var text=$(this).children(":first").text();
			if(text !=""){
				text=" "+text+'点';
			}
			txt+=text;
			$(".firstrow input").val(txt);
			$(this).toggleClass("active");
		})
		var val="";
		$(".bluebg").click(function(){
			var input_txt=$(".firstrow input").val();
			var text=$(this).text();
			input_txt+=text;
			$(".firstrow input").val(input_txt);
			val+=text;
		})
		$("#clearall").click(function(){
			$(this).prev().val("");
			val="";
		})
		$("#backstep").click(function(){
			var input_txt=$(".firstrow input").val();
			var input=input_txt.slice(0,-1);
			$(".firstrow input").val(input);
		})
		$(".bm-btn").click(function () {});
		$(".cm-btn").click(function () {
			$("J_touzhu").val("");
		});
		$(".f").click(function(){
			$(".alert1").show();
			setTimeout( "$('.alert1').fadeOut()" , 1000);
		});
		function a1(){
			$(".openmo").slideToggle();
			$(".maskContent").toggle();
		}
		$(".ufmenu, .ufup").click(function(){
			$(".ufix").animate({height:"0"});
			$("header").show();
		});
		$(".menu").click(function(){
			$(".ufix").animate({height:"100%"});
			$("header").hide();
		});
		$(".qx0").click(function(){
			$(".rmenu").show(300);
			$(this).hide();
			$(".qx45").show();
		});
		$(".qx45").click(function(){
			$(".rmenu").hide(300);
			$(this).hide();
			$(".qx0").show();
		});
		$(".plsm").click(function(){
			$(".peilv").show();
			$(".main, .gmfix").hide();
		});
		$(".pltit span").click(function(){
			$(".peilv").hide();
			$(".main, .gmfix").show();
		});
		function showMask(){
			$("#mask").css("height",$(document).height());
			$("#mask").css("width",$(document).width());
			$("#mask").show();
		}
		function hideMask(){
			$("#mask").hide();
		}
		function curtail(arr) {
			var m = arr.slice(1);
			return m;
		}
		setInterval(counTallNum, 1);
		function counTallNum(){
			var theterm=$('.gmfl').find('.line1').find('b').text();
		}
		$(document).ready(function() {
			$(".scroll-to-bottom").click(function(){
				$(".main").animate({
					scrollTop: $(".main")[0].scrollHeight
				}, 500);
			});
		});
	</script>
	<script>
		function del(id){
			layer.open({
				content: '您确定要取消吗？',
				btn: ['确认', '取消'],
				yes: function(index){
					layer.close(index);
					$.ajax({
						url: "{:U('Home/Run/del')}",
						type: "post",
						data:{'id':id},
						dataType:'json',
						error:function(){
							parent.layer.open({content: '服务器开小差了~',skin: 'msg',time: 2});
						},
						success:function(res){
							location.href=location.href;
						}
					});
				}
			});
		}
	</script>
	<script>
		$(document).ready(function() {
		var $scrollButton = $(".scroll-to-bottom");
		var originalBottom = 100;
		var $digital = $(".digital");
		var keyboardHeight = 0;

		$scrollButton.click(function() {
			var $main = $(".main");
			if ($main.length) {
				$main.animate({
					scrollTop: $main[0].scrollHeight
				}, 500, function() {
					console.log("Scroll completed");
				});
			}
		});

		// 监听模拟键盘打开
		$(".kuitoubtn").click(function() {
			if ($(this).attr("disabled")) {
				layer.open({
					content: '已封盘,禁止投注',
					skin: 'msg',
					time: 2,
					style: 'text-align:center; font-size:16px; color:#fff; background-color:#ff0000; border-radius:5px;'
				});
				return false;
			}
			if (!$digital.hasClass("active")) {
				$digital.removeClass("hide").addClass("active").css("bottom", "0");
				keyboardHeight = $digital.outerHeight() || 300;
				$scrollButton.css("bottom", originalBottom + keyboardHeight + "px");
			}
		});

		// 监听模拟键盘关闭
		$(".maskBody, #canclebtn").click(function() {
			if ($digital.hasClass("active")) {
				$digital.removeClass("active").css("bottom", "-100vw");
				$scrollButton.css("bottom", originalBottom + "px");
				keyboardHeight = 0;
			}
		});

		// 确保图片加载
		$scrollButton.find("img").on("error", function() {
			console.error("Image failed to load: /../img/brush.png");
		});
	});
	// 确保 executeCountDown 与 kuitoubtn 状态同步
	function executeCountDown() {
		if (count <= 0) {
			$(".line2").html("已封盘");
			$('#J_touzhu').attr("disabled", true);
			$("#J_touzhu").css("background-color", "#c7c7c7");
			$('.kuitoubtn').attr("disabled", true);
			$('.kuitoubtn').css("background-color", "#c7c7c7");
		} else {
			count = count - 1;
			var formattedTime = formatSeconds(count);
			$(".line2").html('<span style="color:#ff0000;">' + formattedTime + '</span> <span style="color:#0e9aef">后封盘</span>');
			$('#J_touzhu').attr("disabled", false);
			$("#J_touzhu").css("background-color", "#3da1fe");
			$('.kuitoubtn').attr("disabled", false);
			$('.kuitoubtn').css("background-color", "#10DC60");
		}
	}
	</script>
	<script>
$(document).ready(function() {
    var $main = $(".main");
    var maxMessages = 100; // 限制最大消息数

    // 初始化滚动到最新消息
    $main.scrollTop($main[0].scrollHeight);

    // WebSocket 连接并处理消息
    function connect(port) {
        var socket = io.connect('http://your-server-address:' + port); // 替换为实际服务器地址
        socket.on('connect', function() {
            console.log('Connected to server at 10:39 PM HKT, July 14, 2025');
            socket.emit('joinRoom', { room: 'jnd28' }); // 加入特定房间
        });

        socket.on('newMessage', function(data) {
            var time = new Date().toLocaleTimeString('zh-HK', { hour12: false }); // 使用香港时间格式
            var msgHtml = '';
            if (data.type === 'fk') {
                msgHtml = '<li><div><div class="uhead"><img src="' + (data.head_img_url || '/default_head_img.png') + '" style="pointer-events: none;"></div><div class="betinfo"><p class="uname" style="color:#FF0000">系统接单 (已认证)</p><div class="ubet"><div id="viewall" style="background: #fff;border-radius:3px;padding: 5px;"><p>' + htmlspecialchars(data.content) + '</p></div></div></div></div></li>';
            } else if (data.type === 'say') {
                msgHtml = '<div><div style="color: #A0A2A3;text-align: center;">' + time + '</div><div><div class="uhead"><img src="' + (data.head_img_url || '/default_head_img.png') + '" style="pointer-events: none;"></div><div class="betinfo"><p class="uname">' + htmlspecialchars(data.from_client_name) + '　　</p><div class="ubet"><div id="viewall" style="background: #fff;border-radius:3px;padding: 5px;"><p style="display:flex;">' + htmlspecialchars(data.newmsg) + '</p></div></div></div></div></div>';
            } else if (data.type === 'admin' || data.type === 'system') {
                msgHtml = '<p class="bettime">' + time + '</p><li class="notice"><center>' + htmlspecialchars(data.content) + '</center></li>';
            }
            if (msgHtml) {
                $('#03').append(msgHtml); // 追加到底部
                var messages = $('#03').find('li, div').length;
                if (messages > maxMessages) {
                    $('#03').find('li, div').first().remove(); // 删除最早消息
                }
                // 确保 DOM 更新后滚动
                setTimeout(function() {
                    $main.animate({ scrollTop: $main[0].scrollHeight }, 500);
                }, 0);
            }
        });

        socket.on('betResult', function(data) {
            if (data.success) {
                var time = new Date().toLocaleTimeString('zh-HK', { hour12: false });
                var msg = '<li><div><div class="uhead"><img src="' + (data.head_img_url || '/default_head_img.png') + '" style="pointer-events: none;"></div><div class="betinfo"><p class="uname" style="color:#FF0000">系统接单 (已认证)</p><div class="ubet"><div id="viewall" style="background: #fff;border-radius:3px;padding: 5px;"><p>' + htmlspecialchars(data.bet) + '</p></div></div></div></div></li>';
                $('#03').append('<p class="bettime">' + time + '</p>' + msg);
                var messages = $('#03').find('li, div').length;
                if (messages > maxMessages) {
                    $('#03').find('li, div').first().remove(); // 删除最早消息
                }
                setTimeout(function() {
                    $main.animate({ scrollTop: $main[0].scrollHeight }, 500);
                }, 0);
            } else {
                showAlert("下注失败: " + data.message);
            }
        });

        socket.on('error', function(err) {
            console.error('Socket error:', err);
            showAlert("网络错误，请重试");
        });

        socket.on('connect_error', function(err) {
            console.error('Connection error:', err.message);
            showAlert("连接失败: 请检查网络或服务器");
        });
    }

    // 初始化连接
    connect(15535);

    // 点击滚动到底部按钮
    $(".scroll-to-bottom").click(function() {
        $main.animate({ scrollTop: $main[0].scrollHeight }, 500);
    });

    function htmlspecialchars(str) {
        return str.replace(/&/g, "&").replace(/</g, "<").replace(/>/g, ">").replace(/"/g, """).replace(/'/g, "'");
    }

    function showAlert(message) {
        var alertDiv = document.getElementById("alert");
        if (alertDiv) {
            alertDiv.innerHTML = message;
            $(alertDiv).show();
            setTimeout(function() { $(alertDiv).fadeOut(); }, 2000);
        } else {
            console.error("Alert element not found");
        }
    }
});
function connect(port) {
    var socket = io.connect('http://your-server-address:' + port);
    socket.on('connect', function() {
        console.log('Connected to server');
    });
    socket.on('betResult', function(data) {
        if (data.success) {
            var time = new Date().toLocaleTimeString();
            var msg = '<li><div><div class="uhead"><img src="/default_head_img.png"></div><div class="betinfo"><p class="uname" style="color:#FF0000">系统接单 (已认证)</p><div class="ubet"><div id="viewall" style="background: #fff;border-radius:3px;padding: 5px;"><p>' + htmlspecialchars(data.bet) + '</p></div></div></div></div></li>';
            $('#03').append('<p class="bettime">' + time + '</p>' + msg);
            $('.main').animate({ scrollTop: $('.main')[0].scrollHeight }, 500);
            showAlert("下注成功！");
        } else {
            showAlert("下注失败: " + data.message);
        }
    });
    socket.on('error', function(err) {
        console.error('Socket error:', err);
        showAlert("网络错误，请重试");
    });
}

function htmlspecialchars(str) {
    return str.replace(/&/g, "&").replace(/</g, "<").replace(/>/g, ">").replace(/"/g, """).replace(/'/g, "'");
}

function showAlert(message) {
    document.getElementById("alert").innerHTML = message;
    $(".alert").show();
    setTimeout(function() { $(".alert").fadeOut(); }, 2000);
}
</script>
</body>
</html>
// 天信28,新旗舰28,飞天,名爵,大疆,飞鸟,新圣,大风车,算账机器人系统,客服系统
// TG @D11026104
