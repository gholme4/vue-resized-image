<template>
	<img v-if="resizedSrc" crossorigin="anonymous" :src="resizedSrc" :alt="alt"/>
</template>

<script>

export default {
	name: 'resized-image',
	props: ['src', 'alt', 'width', 'height', 'crop' ],
	data: () => {
		return {
			resizedSrc: null
		}
	},
	methods: {
		resize(currentImage) {
			const img = new Image();

			const width =  this.width ? this.width : 400;
			const height = this.height ? this.height : 400;

			img.setAttribute('crossorigin', 'anonymous'); // works for me
			img.src = currentImage;

			img.onload = () => {
				const scale = Math.max((this.width/img.width),(this.height/img.height));
				const elem = document.createElement('canvas');
				elem.width = width;
				elem.height = height;
				const ctx = elem.getContext('2d');

				if (this.crop)
				{
					const imageWidth = (img.width * scale);
					const imageHeight = (img.height * scale);

					const dx = (width - imageWidth) / 2;
					const dy = (height - imageHeight) / 2;

					ctx.drawImage(img, 0,  0, img.width, img.height, dx, dy, imageWidth, imageHeight);
				}
				else
				{
					ctx.drawImage(img, 0,  0, width, height);
				}

				const dataurl = elem.toDataURL("image/png");
				this.resizedSrc = dataurl;
			};
		}
	},
	mounted: async function() {
		this.resize(this.src);
	},
	watch: { 
        $props: {
			handler() {
				this.resize(this.src);
			},
			deep: true,
			immediate: true,
    	},
    }
}
</script>