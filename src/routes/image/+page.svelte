<script lang="ts">
	import { dev } from '$app/environment';
	import src from './mike-van-den-bos-fbQv3cx--bM-unsplash.jpg';

	const srcset = `/_vercel/image?url=${encodeURIComponent(src)}&w=640&q=85 640w,
     /_vercel/image?url=${encodeURIComponent(src)}&w=828&q=85 828w,
     /_vercel/image?url=${encodeURIComponent(src)}&w=1200&q=85 1200w,
     /_vercel/image?url=${encodeURIComponent(src)}&w=1920&q=85 1920w,
     /_vercel/image?url=${encodeURIComponent(src)}&w=3840&q=85 3840w`;
</script>

<div>
	<h1>Responsive Image</h1>

	<p>
		The bug can be reproduced only when deployed to Vercel because the image optimization API is not
		available locally.
	</p>

	<img
		{src}
		srcset={dev ? undefined : srcset}
		sizes={dev ? undefined : '(max-width: 1024px) 100vw, 1024px'}
		alt="Market Hall in Rotterdam."
		loading="lazy"
	/>
</div>

<style>
	div {
		max-width: 1024px;
		margin: 0 auto;
	}

	img {
		width: 100%;
	}
</style>
