> **"Ethers 'SeamsBeGone' — upload any image, it cuts out the most self-repeating region and reconstructs a seamless tile using only original pixels."**

Here's what each part means:

**"Upload any image"** — you give it any picture: a photo of grass, a brick wall, fabric, a game texture. It all happens in your browser; the image is never sent to a server.

**"It cuts out the most self-repeating region"** — this is the search step. A texture tiles well when some part of it already looks like another part. The tool slides every possible tile width and height across your image and measures, for each candidate, how closely the pixels at one edge agree with the pixels that would wrap around to meet them. The region that agrees best is the "most self-repeating" one, and that's what gets cut out — the *source cut* view shows you exactly where it came from. This is why the output is somewhat smaller than the input: it's a genuine crop, not a resized copy.

**"Reconstructs a seamless tile"** — cutting alone still leaves a faint seam where the tile's right edge meets its left when repeated. The reconstruction step removes it by carving a jagged path through a narrow overlap band, switching from one side to the other exactly where the two sides already look identical — so the join hides inside the texture instead of showing as a straight line.

**"Using only original pixels"** — the part you specifically asked for. Nothing is blended, averaged, mirrored, or synthesized. Every pixel in the downloaded PNG is an untouched pixel copied straight from your uploaded image; the tool only decides *which* pixels to keep and where to cut. (The one optional exception is the "even out lighting" slider, which rescales brightness — it's off by default unless the image has strong light drift.)
