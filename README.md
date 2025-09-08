🌐 Cloudflare Worker Redirect Script

This project provides a simple Cloudflare Worker that performs permanent 301 redirects from an old domain to a new one. It is useful when migrating websites or consolidating multiple blogs into one central domain, while preserving SEO value.

🚀 Features

Redirects all requests from an old domain (e.g., food.volume7.com) to a new domain (e.g., bites.joel.hk).

Keeps the original path and query string intact.

Uses 301 Permanent Redirects to transfer SEO authority.

Lightweight — less than 10 lines of JavaScript.

Deployable directly on Cloudflare Workers
.

📜 Example Code
export default {
  async fetch(request) {
    let url = new URL(request.url)
    url.hostname = "bites.joel.hk"  // new hostname
    return Response.redirect(url.toString(), 301)
  }
}

📖 Usage

Create a Worker in your Cloudflare dashboard.

Paste in the script above.

Add a Route (e.g., food.volume7.com/*).

Point your old subdomain (food.volume7.com) to Cloudflare (CNAME).

Save and deploy! 🎉

All traffic will now automatically redirect to your new site.

💡 Why This Matters

When migrating blogs or recipe sites, broken backlinks can destroy years of SEO. By implementing a redirect at the edge (via Cloudflare Workers), you:

Preserve link equity from old domains.

Ensure visitors never hit 404 pages.

Protect your site’s search engine ranking.

👨‍🍳 About

This Worker was created as part of the migration of my Chinese recipe blog from legacy domains to bites.joel.hk
, where you can find hundreds of traditional and modern recipes in Hong Kong written Chinese.

Visit 👉 joel.hk
 for more projects, articles, and experiments on cooking, automation, and technology.

📌 License

MIT License — feel free to fork, adapt, and use in your own projects. A link back to joel.hk is appreciated 🙌
