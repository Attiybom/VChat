<script>
export default {
	onLaunch: function () {
		console.log('App Launch');
		// #ifdef APP-PLUS-NVUE
		// 加载公共图标库
		const domModule = weex.requireModule('dom');
		domModule.addRule('fontFace', {
			fontFamily: 'iconfont',
			// 下面这个是在线连接，可能会失效，失效时请去阿里矢量图重新制作
			src: "url('https://at.alicdn.com/t/font_1365296_2ijcbdrmsg.ttf')"
		});
		// #endif

		// this.loadIconFont();
	},
	onShow: function () {
		console.log('App Show');
	},
	onHide: function () {
		console.log('App Hide');
	},
	methods: {
		loadIconFont() {
			const domModule = weex.requireModule('dom');
			domModule.addRule('fontFace', {
				fontFamily: 'iconfont',
				// 下面这个是在线连接，可能会失效，失效时请去阿里矢量图重新制作
				src: "url('https://at.alicdn.com/t/font_1365296_2ijcbdrmsg.ttf')"
			});
		}
	}
};
</script>

<style>
/*每个页面公共css */
@import url('./common/free.css');
@import url('./common/common.css');
/* #ifndef APP-PLUS-NVUE */
@import './common/free-icon.css';
/* #endif */
</style>
