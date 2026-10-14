const KEY = "g2g123-seo-2026-a91f7c3e8b2d4a60";
const KEY_FILE = "/g2g123-seo-2026-a91f7c3e8b2d4a60.txt";

export default {
  async fetch(request) {
    const url = new URL(request.url);

    if (url.pathname === KEY_FILE && request.method === "GET") {
      return new Response(KEY, {
        status: 200,
        headers: {
          "Content-Type": "text/plain; charset=utf-8",
          "Cache-Control": "public, max-age=300",
          "X-Content-Type-Options": "nosniff"
        }
      });
    }

    return new Response("Not Found", {
      status: 404,
      headers: {
        "Content-Type": "text/plain; charset=utf-8"
      }
    });
  }
};
