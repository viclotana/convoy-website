<template>
	<div>
		<Header></Header>
		<header class="bg-[url(assets/images/docs-bg.svg)] bg-no-repeat bg-cover h-[450px] w-full"></header>

		<div class="max-w-[1200px] m-auto -mt-270px py-0 px-20px">
			<p class="text-28 font-bold text-center mb-8px text-white-100">Convoy Documentation</p>
			<p class="text-white-100 max-w-[590px] m-auto text-center text-16 mb-40px">
				Find the guides, samples, and references you need to use Convoy to start sending out and receiving webhook events as fast as possible.
			</p>

			<div class="bg-[#fcfcfc] shadow-sm rounded-8px p-24px desktop:flex desktop:justify-between desktop:items-end desktop:flex-nowrap desktop:pt-32px desktop:pr-0 desktop:pb-0 desktop:pl-60px">
				<div>
					<h4 class="mb-16px font-semibold">Overview</h4>
					<p class="text-14 text-grey-40 mb-18px desktop:max-w-[489px]">
						We've put together a short easy to follow steps to get started with deploying Convoy to your environment and sending out webhook events in few minutes.
					</p>
					<div class="mb-40px">
						<nuxt-link to="/docs/introduction" class="flex items-center text-primary-100">
							Read more
							<img src="~/assets/images/arrow-circle-right.svg" class="ml-10px" alt="arrow right" />
						</nuxt-link>
					</div>
				</div>
				<div class="max-w-[385px] -mb-18px rounded-bl-8px">
					<img src="~/assets/images/doc-banner.svg" alt="banner" />
				</div>
			</div>

			<section class="grid grid-cols-[repeat(auto-fill,minmax(333px,_1fr))] gap-24px mb-56px mt-24px">
				<div class="card bg-[#e7fbf4]">
					<h4>Configuration</h4>
					<p>Step by step explanation on how to configure Convoy to best suite your preference and use case.</p>
					<nuxt-link to="/docs/configuration">
						<button class="bg-[#daeee7] rounded-6px">
							Read more
							<img src="~/assets/images/dark-arrow-circle-right.svg" alt="arrow right" />
						</button>
					</nuxt-link>
				</div>

				<div class="card bg-[#ffeeed]">
					<h4>Deployment</h4>
					<p>Learn how to deploy Convoy to any environment of your choice.</p>
					<nuxt-link to="/docs/deploy/install-convoy">
						<button class="bg-[#f5dedc] rounded-6px">
							Read more
							<img src="~/assets/images/dark-arrow-circle-right.svg" alt="arrow right" />
						</button>
					</nuxt-link>
				</div>

				<div class="card bg-[#5a53b3] bg-opacity-10">
					<h4>SDK</h4>
					<p>We went a step further to make it easier to integrate convoy through SDK.</p>
					<nuxt-link to="/docs/sdk">
						<button class="bg-[#e0dfed] rounded-6px">
							Read more
							<img src="~/assets/images/dark-arrow-circle-right.svg" alt="arrow right" />
						</button>
					</nuxt-link>
				</div>

				<div class="card bg-[#fcf5ec]">
					<h4>App Portal</h4>
					<p>With app portal, we're enabling you to extend the visibility our dashboard provides you to your customers.</p>
					<nuxt-link to="/docs/app-portal">
						<button class="bg-[#f2ebe2] rounded-6px">
							Read more
							<img src="~/assets/images/dark-arrow-circle-right.svg" alt="arrow right" />
						</button>
					</nuxt-link>
				</div>
				<div class="card bg-[#d1efff]">
					<h4>Api Reference</h4>
					<p>The API reference provides you with the available endpoints to interact with Convoy.</p>
					<a href="https://convoy.readme.io/" target="_blank">
						<button class="bg-[#c1e1f2] rounded-6px">
							Read More
							<img src="~/assets/images/dark-arrow-circle-right.svg" alt="arrow right" />
						</button>
					</a>
				</div>
			</section>
		</div>

		<Footer></Footer>
	</div>
</template>

<script>
export default {
	scrollToTop: true,
	head() {
		return {
			title: 'Convoy Documentation',
			meta: [
				{ hid: 'description', name: 'description', content: 'Reliable Webhooks Gateway for sending and receiving millions of webhooks securely with support for Retries, Rate Limiting, Static IPs, Circuit Breaking and scalability for efficient engineering teams.' },
				{
					hid: 'apple-mobile-web-app-title',
					name: 'apple-mobile-web-app-title',
					content: 'Convoy Documentation'
				},
				{ hid: 'og:title', name: 'og:title', content: 'Convoy Documentation' },
				{ hid: 'og:site_name', name: 'og:site_name', content: 'Convoy' },
				{ hid: 'og:type', name: 'og:type', content: 'website' },
				{
					hid: 'og:description',
					name: 'og:description',
					content: 'Reliable Webhooks Gateway for sending and receiving millions of webhooks securely with support for Retries, Rate Limiting, Static IPs, Circuit Breaking and scalability for efficient engineering teams.'
				},
				{
					hid: 'og:url',
					name: 'og:url',
					content: `https://getconvoy.io/docs`
				},
				{
					hid: 'twitter:title',
					name: 'twitter:title',
					content: 'Convoy Documentation'
				},
				{
					hid: 'twitter:url',
					name: 'twitter:url',
					content: `https://getconvoy.io/docs`
				},
				{
					hid: 'twitter:text:title',
					name: 'twitter:text:title',
					content: 'Convoy Documentation'
				},
				{
					hid: 'twitter:description',
					name: 'twitter:description',
					content: 'Reliable Webhooks Gateway for sending and receiving millions of webhooks securely with support for Retries, Rate Limiting, Static IPs, Circuit Breaking and scalability for efficient engineering teams.'
				}
			],
			link: [{ hid: 'canonical', rel: 'canonical', href: `https://getconvoy.io/docs` }]
		};
	}
};
</script>

<style lang="scss" scoped>
.card {
	@apply rounded-16px p-32px;

	h4 {
		@apply font-semibold mb-16px;
	}

	p {
		@apply text-14 text-[#7987a3] max-w-[293px] mb-24px min-h-[72px];
	}

	button {
		@apply text-14 font-medium px-24px py-10px flex items-center text-[#46548c];

		img {
			@apply ml-10px w-16px h-16px;
		}
	}
}
</style>
