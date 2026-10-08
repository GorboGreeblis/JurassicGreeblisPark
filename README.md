# Jurassic Greeblis Park

A VR (Meta Quest browser) game built on the **Greeblis City** engine. Everything is in
one self-contained file: `index.html`.

The engine came from Greeblis City unchanged: talking, Blossoms, dance battles, shop,
concert/finale, pizza phone, wandering AI and the VR UI. A "Jurassic layer" on top swaps
in a prehistoric clearing, dinosaur models and placeholder text.

## Running

Serve the folder over HTTP(S), for example `python3 -m http.server`, then open `index.html`.

- **Quest browser:** press A to enter VR, the same as Greeblis City.
- **Desktop browser:** loads the **temporary third-person desktop test mode**. Use it for
  testing only. On a Quest you can force it with `index.html?desktop=1`.

| Desktop control | Action |
| --- | --- |
| WASD / arrow keys | move |
| drag mouse, or Q / E | orbit camera |
| mouse wheel | zoom |
| click | point and select (creatures, menus, panel buttons) |
| F | talk to the nearest creature |
| G | give a Blossom to the nearest creature |
| Space / Enter | advance dialogue or confirm |
| 1–9 | pick a menu or panel option |
| Esc | close a menu or panel |

Add `?debug=1` to show caught errors and debug toasts.

## Where things live in `index.html`

The original file was a compressed, minified bundle. It has been unpacked and
pretty-printed so it can be edited. The engine code still uses the original short
minified names.

- **`JGP` block** (search for `JURASSIC GREEBLIS PARK LAYER`). This is where you edit content:
  - `CAST`: one entry per creature (name, body plan, colours, scale).
  - `PLANS`: the generic dinosaur body plans (raptor, rex, longneck, trike, proto, stego,
    ankylo, para, pachy, spino, dilo, ptero).
  - `L3()`, the `gift` and `campfire` lines, and `battleText()`: placeholder dialogue,
    Blossom replies and battle text.
  - `swapWorld()`: the prehistoric clearing (terrain, jungle ring, rocks, ferns, mountains,
    volcano). It keeps the working stations: stage/concert, shop, pond, phone and sign.
- **Desktop test mode** (search for `JGP DESKTOP TEST MODE`). This code is self-contained
  inside the XR module, so it can be deleted later without touching the VR code.

## Placeholder content

- Every creature says `Placeholder line 1/2/3`.
- Every creature offers the Blossom option ("Give an electric blossom") and replies
  `Placeholder blossom line`.
- The dance-battle system is unchanged. All of its text (titles, moves, misses, run/win
  lines, bar label) is placeholder text.
