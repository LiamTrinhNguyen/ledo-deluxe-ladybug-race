<p align="center">
  <img src="public/connection.svg" alt="How devices connect in Ludo Delux: a short handshake through Vercel and Neon, then dice and moves go directly between the players' devices" width="100%"/>
</p>

<p align="center">
  <img src="public/ludo-delux-mark.png" alt="Ludo Delux" width="160"/>
</p>

<h1 align="center">Ludo Delux</h1>

<p align="center">
  A ladybug race for 3 to 10 players.<br/>
  Classic or Wild. Your phone keeps your name. The room only borrows a code.
</p>

<p align="center">
  <a href="https://github.com/LiamTrinhNguyen/ledo-deluxe-ladybug-race/issues">Ideas and suggestions</a>
  ·
  <a href="#support-the-project">Sponsor</a>
  ·
  <a href="#privacy">Privacy</a>
  ·
  <a href="https://vercel.com">Vercel</a>
  ·
  <a href="https://console.neon.tech">Neon Console</a>
</p>

<p align="center">
  <a href="https://github.com/sponsors/LiamTrinhNguyen"><img src="https://img.shields.io/badge/Sponsor-%E2%9D%A4-e08a4f?logo=githubsponsors&logoColor=white" alt="Sponsor Liam TrinhNguyen on GitHub"/></a>
</p>

---

## What it is

Ludo Delux is a clockwise race. Each seat has four ladybugs. A 6 leaves the yard. The die must match the distance to send another colour home. Walking past does nothing. Two of one colour on a normal square make a fortress. Twenty seconds a turn.

Wild adds a rocket, a black hole, a golden die, and suffer. The host can turn each one off before the game starts.

Play on the web, or from the iPhone build prepared for the App Store. A game against machine players never leaves the device. A room with other people connects the phones directly after a short handshake.

## How a room connects

The banner at the top of this page shows the two steps.

1. **Handshake.** Each device asks the mailbox on Vercel who is in the room. Vercel keeps that short list in Neon and clears it within 60 seconds.
2. **Realtime.** Every device then links directly to every other. The host applies each move and sends the board to all. Dice and moves do not pass through Vercel or Neon.

When two devices cannot reach each other directly, a Cloudflare relay carries that one link. The traffic stays encrypted.

## Stack

| Piece | Where |
|---|---|
| App | TypeScript, React, Vite |
| Phone build | Capacitor |
| Hosting | [Vercel](https://vercel.com) |
| Temporary room data | [Neon](https://console.neon.tech) Postgres |
| After the handshake | Direct connection between the players' devices |
| When no direct path exists | Cloudflare relay |

## Support the project

Ludo Delux is a personal project. It has no ads and nothing to buy. Some of the pieces that keep it running cost money: the hosting, the database, the relay that helps phones on difficult networks connect, and the developer account needed to publish the iPhone app.

If you enjoy the game and want to help keep it online, you can sponsor it here:

**[github.com/sponsors/LiamTrinhNguyen](https://github.com/sponsors/LiamTrinhNguyen)**

Any amount helps, and it goes to those running costs first. Thank you.

## Ideas and suggestions

Open an issue: [github.com/LiamTrinhNguyen/ledo-deluxe-ladybug-race/issues](https://github.com/LiamTrinhNguyen/ledo-deluxe-ladybug-race/issues)

Use that list for a rule that feels wrong, a board that does not fit the phone, or a feature you want next. One issue per idea.

## Privacy

Last updated: November 15, 2026.

The App Store listing points at this same policy, also shown in the app at `/privacy`.

### Summary

Ludo Delux has no accounts, no advertising, and no analytics. We do not sell or share personal information.

### What stays on your device

The name you type and a random id for your device are saved on your device only, so the game can remember you next time. A game against machine players never leaves your device.

### What happens when you join a room

To connect players, our server briefly holds the room code, a temporary random connection id, and the connection messages your device exchanges with the other players. These messages include network addresses. Each message is deleted as soon as it is delivered, or after 60 seconds, and a player is removed from the room list after 30 seconds of inactivity.

After that, the game runs directly between the players' devices. Your name, your device id, and your moves are sent to the other players in your room, and their devices can see your network address, as with any direct connection. Our server does not receive them.

When two devices cannot reach each other directly, their connection is carried by a relay run by Cloudflare. The relay passes the encrypted traffic along and cannot read your name or your moves.

### Services we rely on

The game is hosted by [Vercel](https://vercel.com) and uses a [Neon](https://console.neon.tech) database for the temporary room data above. STUN and relay servers run by Google and Cloudflare help devices find and reach each other, and fonts are loaded from Google Fonts. Like any internet service, these providers see the network address of devices that contact them.

### Children

The game does not ask for or knowingly collect personal information from anyone, including children.

### Contact

Questions about this policy: [Liamtrinhnguyen@gmail.com](mailto:Liamtrinhnguyen@gmail.com)

---

Built by [Liam TrinhNguyen](https://github.com/LiamTrinhNguyen). If the game made you smile, [sponsoring](https://github.com/sponsors/LiamTrinhNguyen) helps keep it running.
