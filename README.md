<p align="center">
  <img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:E05561,100:7A1C2B&height=200&section=header&text=Hoang%20Tri&fontSize=56&fontColor=ffffff&fontAlignY=36&desc=Full-stack%20developer%20%C2%B7%20building%20Livi%20Photobooth&descSize=18&descAlignY=58&animation=fadeIn" />
</p>

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&pause=1200&color=E05561&center=true&vCenter=true&width=640&lines=Hi%2C+I'm+hippi+%F0%9F%91%8B;From+the+touchscreen+to+the+database;Kiosks+%C2%B7+booking+%C2%B7+payments+%C2%B7+printing" alt="Hi, I'm hippi" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Focus-Full--stack-E05561?style=flat-square" />
  <img src="https://img.shields.io/badge/Now-Livi_Photobooth-7A1C2B?style=flat-square" />
  <img src="https://komarev.com/ghpvc/?username=Hoangtri20003&label=Profile%20views&color=E05561&style=flat-square" />
</p>

I build products end to end — the touchscreen a guest taps, the hardware behind it, and the API and database that keep it all honest. Right now that is **Livi**: a photobooth chain with photo kiosks, a booking kiosk, cash & QR payments and photo printing.

### 🛠️ Tech Stack

<p align="center">
  <img src="https://skillicons.dev/icons?i=ts,js,react,nextjs,electron,nodejs,nestjs,express,tailwind,figma&perline=10&theme=dark" />
  <br/>
  <img src="https://skillicons.dev/icons?i=mongodb,redis,prisma,docker,vercel,cloudflare,jest,vitest,git,github&perline=10&theme=dark" />
</p>

### 🚀 Featured Projects

<table>
  <tr>
    <td width="50%" valign="top">
      <h4>📸 Livi Photobooth</h4>
      <p>Photo kiosks (Electron + Next.js) with Canon live view and DNP printing, a landscape booking kiosk with cash and bank-transfer payments, and a NestJS backend + admin dashboard.</p>
      <p><img src="https://img.shields.io/badge/Electron-47848F?style=flat-square&logo=electron&logoColor=white" /> <img src="https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white" /> <img src="https://img.shields.io/badge/NestJS-E0234E?style=flat-square&logo=nestjs&logoColor=white" /> <img src="https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white" /></p>
      <sub>Private · in production</sub>
    </td>
    <td width="50%" valign="top">
      <h4>🧳 <a href="https://github.com/TRIPPIO-Smart-Booking-System/TRIPPIO_FE">TRIPPIO</a></h4>
      <p>Smart booking system — web front end. <a href="https://trippio-fe.vercel.app">Live demo ↗</a></p>
      <p><img src="https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white" /> <img src="https://img.shields.io/badge/Prisma-2D3748?style=flat-square&logo=prisma&logoColor=white" /> <img src="https://img.shields.io/badge/Tailwind-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white" /></p>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <h4>🎨 <a href="https://github.com/zus-pop/artchain-mobile">ArtChain Mobile</a></h4>
      <p>Mobile app built with Expo and React Native.</p>
      <p><img src="https://img.shields.io/badge/Expo-000020?style=flat-square&logo=expo&logoColor=white" /> <img src="https://img.shields.io/badge/React_Native-20232A?style=flat-square&logo=react&logoColor=61DAFB" /> <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" /></p>
    </td>
    <td width="50%" valign="top">
      <h4>⚡ <a href="https://github.com/Hoangtri20003/Be-Ev-rental-system">EV Rental — Backend</a></h4>
      <p>REST API with real-time updates for an electric-vehicle rental system.</p>
      <p><img src="https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white" /> <img src="https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white" /> <img src="https://img.shields.io/badge/Socket.io-010101?style=flat-square&logo=socketdotio&logoColor=white" /></p>
    </td>
  </tr>
</table>

### 🏗️ Livi — how it's built

A shop runs one **booking kiosk** and a **photo kiosk per booth**. They never talk to each other directly: everything goes through the API. A guest books and pays at the booking kiosk, carries the printed QR ticket to a booth, scans it and shoots.

```mermaid
%%{init: {'theme':'base','themeVariables':{'fontFamily':'ui-sans-serif, system-ui','fontSize':'15px','lineColor':'#8B949E','primaryTextColor':'#F0F6FC','clusterBkg':'#161B22','clusterBorder':'#30363D','edgeLabelBackground':'#0D1117'}}}%%
flowchart TB
  subgraph Shop["🏪 In the shop"]
    direction LR
    CASH["💵 Bill acceptor<br/><small>RS232</small>"] --> BK["🧾 Booking kiosk<br/><small>Electron · Next.js</small>"]
    BK --> TP["🖨️ Thermal printer<br/><small>ESC/POS</small>"]
    TP -. "QR ticket" .-> QR["🔍 QR scanner<br/><small>USB HID</small>"]
    QR --> PK["📸 Photo kiosk<br/><small>Electron · Next.js</small>"]
    CAM["📷 Canon camera<br/><small>EDSDK</small>"] --> PK
    PK --> DNP["🖼️ DNP printer<br/><small>Hot Folder Print</small>"]
  end
  subgraph Cloud["☁️ Cloud"]
    direction LR
    ADMIN["🖥️ Admin web<br/><small>Next.js · Vercel</small>"] <--> API["⚙️ API<br/><small>NestJS · Railway</small>"]
    API --> DB[("🍃 MongoDB Atlas")]
    API --> R2[("🪣 Cloudflare R2")]
    API --> REDIS[("⚡ Redis")]
  end
  BK <-->|"book · pay"| API
  PK <-->|"check in · upload"| API
  API <-->|"bank transfer"| PAY["💳 payOS"]
  API -->|"emails"| MAIL["✉️ Brevo"]

  classDef shop fill:#3A1219,stroke:#E05561,stroke-width:2px,color:#F0F6FC;
  classDef cloud fill:#0F2A44,stroke:#58A6FF,stroke-width:2px,color:#F0F6FC;
  classDef store fill:#13261B,stroke:#3FB950,stroke-width:2px,color:#F0F6FC;
  classDef ext fill:#161B22,stroke:#8B949E,stroke-width:1.5px,stroke-dasharray:5 4,color:#F0F6FC;
  class CASH,BK,TP,QR,PK,CAM,DNP shop;
  class ADMIN,API cloud;
  class DB,R2,REDIS store;
  class PAY,MAIL ext;
```

<details>
<summary><b>Every technology, part by part</b></summary>
<br/>

<table>
  <tr>
    <td width="22%"><b>📸 Photo kiosk</b></td>
    <td><img src="https://img.shields.io/badge/Electron-47848F?style=flat-square&logo=electron&logoColor=white" /> <img src="https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white" /> <img src="https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB" /> <img src="https://img.shields.io/badge/Zustand-443E38?style=flat-square&logo=react&logoColor=white" /> <img src="https://img.shields.io/badge/TanStack_Query-FF4154?style=flat-square&logo=reactquery&logoColor=white" /> <img src="https://img.shields.io/badge/Framer_Motion-0055FF?style=flat-square&logo=framer&logoColor=white" /> <img src="https://img.shields.io/badge/Tailwind-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white" /> <img src="https://img.shields.io/badge/Lottie-00DDB3?style=flat-square&logo=lottiefiles&logoColor=white" /> <img src="https://img.shields.io/badge/sharp-99CC00?style=flat-square&logo=sharp&logoColor=white" /> <img src="https://img.shields.io/badge/FFmpeg-007808?style=flat-square&logo=ffmpeg&logoColor=white" /> <img src="https://img.shields.io/badge/Canon_EDSDK_(N--API)-CC0000?style=flat-square&logo=canon&logoColor=white" /> <img src="https://img.shields.io/badge/serialport-3C873A?style=flat-square&logo=nodedotjs&logoColor=white" /></td>
  </tr>
  <tr>
    <td width="22%"><b>🧾 Booking kiosk</b></td>
    <td><img src="https://img.shields.io/badge/Electron-47848F?style=flat-square&logo=electron&logoColor=white" /> <img src="https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white" /> <img src="https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB" /> <img src="https://img.shields.io/badge/Zustand-443E38?style=flat-square&logo=react&logoColor=white" /> <img src="https://img.shields.io/badge/TanStack_Query-FF4154?style=flat-square&logo=reactquery&logoColor=white" /> <img src="https://img.shields.io/badge/Framer_Motion-0055FF?style=flat-square&logo=framer&logoColor=white" /> <img src="https://img.shields.io/badge/Lottie-00DDB3?style=flat-square&logo=lottiefiles&logoColor=white" /> <img src="https://img.shields.io/badge/Bill_acceptor_RS232-3C873A?style=flat-square&logo=nodedotjs&logoColor=white" /> <img src="https://img.shields.io/badge/ESC%2FPOS_printing-555555?style=flat-square&logo=printables&logoColor=white" /></td>
  </tr>
  <tr>
    <td width="22%"><b>⚙️ Backend API</b></td>
    <td><img src="https://img.shields.io/badge/NestJS-E0234E?style=flat-square&logo=nestjs&logoColor=white" /> <img src="https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white" /> <img src="https://img.shields.io/badge/Mongoose-880000?style=flat-square&logo=mongoose&logoColor=white" /> <img src="https://img.shields.io/badge/JWT_%2B_Passport-000000?style=flat-square&logo=jsonwebtokens&logoColor=white" /> <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white" /> <img src="https://img.shields.io/badge/Swagger-85EA2D?style=flat-square&logo=swagger&logoColor=black" /> <img src="https://img.shields.io/badge/payOS-1A73E8?style=flat-square&logo=cashapp&logoColor=white" /> <img src="https://img.shields.io/badge/Brevo_email-0B996E?style=flat-square&logo=brevo&logoColor=white" /> <img src="https://img.shields.io/badge/S3_SDK_→_R2-F38020?style=flat-square&logo=amazons3&logoColor=white" /></td>
  </tr>
  <tr>
    <td width="22%"><b>🖥️ Admin dashboard</b></td>
    <td><img src="https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white" /> <img src="https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB" /> <img src="https://img.shields.io/badge/TanStack_Query-FF4154?style=flat-square&logo=reactquery&logoColor=white" /> <img src="https://img.shields.io/badge/Tailwind_v4-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white" /> <img src="https://img.shields.io/badge/QR_codes-000000?style=flat-square&logo=qrcode&logoColor=white" /></td>
  </tr>
  <tr>
    <td width="22%"><b>☁️ Infra & quality</b></td>
    <td><img src="https://img.shields.io/badge/Railway-0B0D0E?style=flat-square&logo=railway&logoColor=white" /> <img src="https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white" /> <img src="https://img.shields.io/badge/MongoDB_Atlas-47A248?style=flat-square&logo=mongodb&logoColor=white" /> <img src="https://img.shields.io/badge/Cloudflare_R2-F38020?style=flat-square&logo=cloudflare&logoColor=white" /> <img src="https://img.shields.io/badge/Vitest-6E9F18?style=flat-square&logo=vitest&logoColor=white" /> <img src="https://img.shields.io/badge/Jest-C21325?style=flat-square&logo=jest&logoColor=white" /> <img src="https://img.shields.io/badge/Playwright-2EAD33?style=flat-square&logo=playwright&logoColor=white" /> <img src="https://img.shields.io/badge/Husky_%2B_lint--staged-42B883?style=flat-square&logo=git&logoColor=white" /></td>
  </tr>
</table>

</details>

### 📊 GitHub Stats

<p align="center">
  <img height="165" src="https://github-readme-stats.vercel.app/api?username=Hoangtri20003&show_icons=true&count_private=true&include_all_commits=true&theme=tokyonight&hide_border=true&bg_color=0D1117&title_color=E05561&icon_color=E05561&ring_color=E05561" />
  <img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Hoangtri20003&layout=compact&theme=tokyonight&hide_border=true&bg_color=0D1117&title_color=E05561" />
</p>
<p align="center">
  <img src="https://streak-stats.demolab.com?user=Hoangtri20003&theme=tokyonight&hide_border=true&background=0D1117&ring=E05561&fire=E05561&currStreakLabel=E05561" />
</p>

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Hoangtri20003/Hoangtri20003/output/github-snake-dark.svg" />
    <img alt="Contribution snake" src="https://raw.githubusercontent.com/Hoangtri20003/Hoangtri20003/output/github-snake.svg" />
  </picture>
</p>

<p align="center">
  <img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:7A1C2B,100:E05561&height=110&section=footer" />
</p>
