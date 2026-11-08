# 🚀🚀🚀 Duix Avatar — Truly open-source AI avatar toolkit for offline video generation and digital human cloning

🔗 **Office website:** [www.duix.com](http://www.duix.com)

# Table of Contents

1. [What's Duix.Avatar](#1-whats-Duix.Avatar)
2. [Introduction](#2-introduction)
3. [How to Run Locally](#3-how-to-run-locally)
4. [Open APIs](#4-open-apis)
5. [What's New](#5-whats-new)
6. [FAQ](#6-faq)
7. [How to Interact in real time](#7-how-to-interact-in-real-time)
8. [Contact](#8-contact)
9. [License](#9-license)
10. [Acknowledgments](#10-acknowledgments)
11. [Star History](#11-star-history)

------

## 1. What's Duix.Avatar

**Duix.Avatar** is a free and open-source AI avatar project developed by **Duix.com**.

Seven years ago, a group of young pioneers chose an unconventional technical path, developing a method to train digital human models using real-person video data. Unlike traditional costly 3D digital human approaches, we leveraged AI-generated technology to create ultra-realistic digital humans, slashing production costs from hundreds of thousands of dollars to just $1,000. This innovation has empowered over 10,000 enterprises and generated over 500,000 personalized avatars for professionals across fields – educators, content creators, legal experts, medical practitioners, and entrepreneurs – dramatically enhancing their video production efficiency. However, our vision extends beyond commercial applications. We believe this transformative technology should be accessible to everyone. To democratize digital human creation, we've open-sourced our cloning technology and video production framework. Our commitment remains: breaking down technological barriers to make cutting-edge tools available to all. Now, anyone with a computer can freely craft their own AI Avatar and produce videos at zero cost – this is the essence of  **Duix.Avatar**.

## 2. Introduction

![img](README.assets/2.png)

Duix.Avatar is a fully offline video synthesis tool designed for Windows systems that can precisely clone your appearance and voice, digitalizing your image. You can create videos by driving virtual avatars through text and voice. No internet connection is required, protecting your privacy while enjoying convenient and efficient digital experiences.

- Core Features
  - Precise Appearance and Voice Cloning: Using advanced AI algorithms to capture human facial features with high precision, including facial features, contours, etc., to build realistic virtual models. It can also precisely clone voices, capturing and reproducing subtle characteristics of human voices, supporting various voice parameter settings to create highly similar cloning effects.
  - Text and Voice-Driven Virtual Avatars: Understanding text content through natural language processing technology, converting text into natural and fluent speech to drive virtual avatars. Voice input can also be used directly, allowing virtual avatars to perform corresponding actions and facial expressions based on the rhythm and intonation of the voice, making the virtual avatar's performance more natural and vivid.
  - Efficient Video Synthesis: Highly synchronizing digital human video images with sound, achieving natural and smooth lip-syncing, intelligently optimizing audio-video synchronization effects.
  - Multi-language Support: Scripts support eight languages - English, Japanese, Korean, Chinese, French, German, Arabic, and Spanish.
- Key Advantages
  - Fully Offline Operation: No internet connection required, effectively protecting user privacy, allowing users to create in a secure, independent environment, avoiding potential data leaks during network transmission.
  - User-Friendly: Clean and intuitive interface, easy to use even for beginners with no technical background, quickly mastering the software's usage to start their digital human creation journey.
  - Multiple Model Support: Supports importing multiple models and managing them through one-click startup packages, making it convenient for users to choose suitable models based on different creative needs and application scenarios.
- Technical Support
  - Voice Cloning Technology: Using advanced technologies like artificial intelligence to generate similar or identical voices based on given voice samples, covering context, intonation, speed, and other aspects of speech.
  - Automatic Speech Recognition: Technology that converts human speech vocabulary content into computer-readable input (text format), enabling computers to "understand" human speech.
  - Computer Vision Technology: Used in video synthesis for visual processing, including facial recognition and lip movement analysis, ensuring virtual avatar lip movements match voice and text content.



## 3. How to Run Locally

Duix.Avatar supports Docker-based rapid deployment. Prior to deployment, ensure your hardware and software environments meet the specified requirements.

Duix.Avatar support two deployment modes：Windows / Ubuntu 22.04 Installation

### **Dependencies**

1. Nodejs 18
2. Docker Images
   - docker pull guiji2025/fun-asr
   - docker pull guiji2025/fish-speech-ziming
   - docker pull guiji2025/duix.avatar



### Mode 1：Windows Installation

**System Requirements:**

- Currently supports Windows 10 19042.1526 or higher

**Hardware Requirements：**

- Must have D Drive: Mainly used for storing digital human and project data
  - Free space requirement: More than 30GB
- C Drive: Used for storing service image files
  - Free space requirement: More than 100GB
  - If less than 100GB is available, after installing Docker, you can choose a different disk folder with more than 100GB of remaining space at the location shown below.

    ![img](README.assets/7.png)

- Recommended Configuration:
  - CPU: 13th Gen Intel Core i5-13400F
  - Memory: 32GB
  - Graphics Card: RTX 4070
- Ensure you have an NVIDIA graphics card with properly installed drivers

  > NVIDIA driver download link: https://www.nvidia.cn/drivers/lookup/

  ![img](./README.assets/14.png)


#### **Installing Windows Docker**

1. Use the command `wsl --list --verbose` to check if WSL is installed. If it shows as below, it's already installed and no further installation is needed.

    ![img](README.assets/11.png)



2. Update WSL using `wsl --update`.

    ![img](README.assets/10.png)

3. [Download Docker for Windows](https://www.docker.com/), choose the appropriate installation package based on your CPU architecture.
4. When you see this interface, installation is successful.

    ![img](README.assets/5.png)

5. Run Docker

    ![img](README.assets/12.png)

6. Accept the agreement and skip login on first run

    ![img](README.assets/8.png)

    ![img](README.assets/13.png)

    ![img](README.assets/3.png)


#### **Installing the Server**

Installation using Docker, docker-compose as follows:

1. The `docker-compose.yml` file is in the `/deploy` directory.
2. Execute `docker-compose up -d` in the `/deploy` directory, if you want to use the lite version, execute `docker-compose -f docker-compose-lite.yml up -d`
3. Wait patiently (about half an hour, speed depends on network), download will consume about 70GB of traffic, make sure to use WiFi
4. When you see three services in Docker, it indicates success (the lite version has only one service `Duix.Avatar-gen-video`)

    ![img](README.assets/6.png)

#### **Server Deployment Solution for NVIDIA 50 Series Graphics Cards**

For 50 series graphics cards (tested and also works for 30/40 series with CUDA 12.8) Uses the official preview version of PyTorch

#### **Client**

1. Directly download the [officially built installation package](https://github.com/duixcom/Duix.Avatar/releases)
2. Double-click `Duix.Avatar-x.x.x-setup.exe` to install

### Mode 2：Ubuntu 22.04 Installation

**System Requirements：**

We have conducted a complete test on **Ubuntu 22.04**. However, theoretically, it supports desktop Linux distributions.

**Hardware Requirements：**

- Recommended Configuration
- CPU: 13th Generation Intel Core i5 - 13400F
- Memory: 32G or more (necessary)
- Graphics Card: RTX - 4070 (Ensure you have an NVIDIA graphics card and the graphics card driver is correctly installed)
- Hard Disk: Free space greater than 100G

**Install Docker:**

First, use` docker --version` to check if Docker is installed. If it is installed, skip the following steps.

```
sudo apt update
sudo apt install docker.io
sudo apt install docker-compose
```

**Install the graphics card driver:**

1. Install the graphics card driver by referring to the official documentation(https://www.nvidia.cn/drivers/lookup/).

After installation, execute the `nvidia-smi` command. If the graphics card information is displayed, the installation is successful.

2. Install the NVIDIA Container Toolkit

​    The NVIDIA Container Toolkit is a necessary tool for Docker to use NVIDIA GPUs. The installation steps are as follows:

- Add the NVIDIA package repository:

```
distribution=$(. /etc/os-release;echo $ID$VERSION_ID) \
  && curl -s -L https://nvidia.github.io/libnvidia-container/gpgkey | sudo apt-key add - \
  && curl -s -L https://nvidia.github.io/libnvidia-container/$distribution/libnvidia-container.list | sudo tee /etc/apt/sources.list.d/nvidia-container-toolkit.list
```

- Update the package list and install the toolkit:

```
sudo apt-get update
sudo apt-get install -y nvidia-container-toolkit
```

- Configure Docker to use the NVIDIA runtime:

```
sudo nvidia-ctk runtime configure --runtime=docker
{"returncode":0,"stdout":"export default function Home() {\n  return <main style={{ minHeight: \"100vh\", background: \"#090a0d\", color: \"#f5f5f5\", display: \"grid\", placeItems: \"center\", fontFamily: \"system-ui\" }}>\n    <div><h1>AI Episode Studio API</h1><p>Backend is running. Open the Expo mobile app to create episodes.</p></div>\n  </main>;\n}\n=== api/assets/[key]/route.ts\nimport { NextRequest, NextResponse } from \"next/server\";\nimport { prisma } from \"@/lib/prisma\";\nimport { requireUser, jsonError } from \"@/lib/http\";\nimport { storage } from \"@/storage\";\ntype Ctx = { params: Promise<{ key: string }> };\nexport async function GET(req: NextRequest, ctx: Ctx) {\n  try {\n    const uid = await requireUser(req); const { key } = await ctx.params;\n    const owned = await prisma.fraction.findFirst({\n      where: { OR: [{ videoAssetKey: key }, { lastFrameKey: key }], scene: { episode: { season: { project: { ownerId: uid } } } } }\n    });\n    if (!owned) throw new Error(\"not-found\");\n    const data = await storage.get(key);\n    return new NextResponse(new Uint8Array(data), { headers: { \"Content-Type\": key.endsWith(\".mp4\") ? \"video/mp4\" : \"application/octet-stream\", \"Cache-Control\": \"private, no-store\" } });\n  } catch (e) { return jsonError(e); }\n}\n\n=== api/auth/login/route.ts\nimport { NextRequest, NextResponse } from \"next/server\";\nimport bcrypt from \"bcryptjs\";\nimport { prisma } from \"@/lib/prisma\";\nimport { credentialsSchema } from \"@/lib/schemas\";\nimport { makeToken } from \"@/lib/auth\";\nimport { jsonError } from \"@/lib/http\";\n\nexport async function POST(req: NextRequest) {\n  try {\n    const input = credentialsSchema.parse(await req.json());\n    const user = await prisma.user.findUnique({ where: { email: input.email.toLowerCase() } });\n    if (!user || !(await bcrypt.compare(input.password, user.passwordHash))) throw new Error(\"unauthorized\");\n    const token = await makeToken(user.id);\n    const response = NextResponse.json({ user: { id: user.id, email: user.email }, token });\n    response.cookies.set(\"session\", token, { httpOnly: true, secure: process.env.NODE_ENV === \"production\", sameSite: \"lax\", path: \"/\", maxAge: 60 * 60 * 24 * 30 });\n    return response;\n  } catch (e) { return jsonError(e); }\n}\n\n=== api/auth/logout/route.ts\nimport { NextResponse } from \"next/server\";\nexport async function POST() {\n  const response = NextResponse.json({ ok: true });\n  response.cookies.set(\"session\", \"\", { httpOnly: true, path: \"/\", maxAge: 0 });\n  return response;\n}\n\n=== api/auth/register/route.ts\nimport { NextRequest, NextResponse } from \"next/server\";\nimport bcrypt from \"bcryptjs\";\nimport { prisma } from \"@/lib/prisma\";\nimport { credentialsSchema } from \"@/lib/schemas\";\nimport { makeToken } from \"@/lib/auth\";\nimport { jsonError } from \"@/lib/http\";\n\nexport async function POST(req: NextRequest) {\n  try {\n    const input = credentialsSchema.parse(await req.json());\n    const passwordHash = await bcrypt.hash(input.password, 12);\n    const user = await prisma.user.create({ data: { email: input.email.toLowerCase(), passwordHash }, select: { id: true, email: true } });\n    const token = await makeToken(user.id);\n    const response = NextResponse.json({ user, token });\n    response.cookies.set(\"session\", token, { httpOnly: true, secure: process.env.NODE_ENV === \"production\", sameSite: \"lax\", path: \"/\", maxAge: 60 * 60 * 24 * 30 });\n    return response;\n  } catch (e) { return jsonError(e); }\n}\n\n=== api/episodes/[id]/scenes/route.ts\nimport { NextRequest, NextResponse } from \"next/server\";\nimport { prisma } from \"@/lib/prisma\";\nimport { requireUser, jsonError } from \"@/lib/http\";\nimport { sceneSchema } from \"@/lib/schemas\";\ntype Ctx = { params: Promise<{ id: string }> };\nexport async function GET(req: NextRequest, ctx: Ctx) {\n  try { const uid = await requireUser(req); const { id } = await ctx.params;\n    const episode = await prisma.episode.findFirst({ where: { id, season: { project: { ownerId: uid } } } });\n    if (!episode) throw new Error(\"not-found\");\n    const scenes = await prisma.scene.findMany({ where: { episodeId: id }, orderBy: { number: \"asc\" }, include: { fractions: { orderBy: { number: \"asc\" } } } });\n    return NextResponse.json({ scenes });\n  } catch (e) { return jsonError(e); }\n}\nexport async function POST(req: NextRequest, ctx: Ctx) {\n  try { const uid = await requireUser(req); const { id } = await ctx.params;\n    const episode = await prisma.episode.findFirst({ where: { id, season: { project: { ownerId: uid } } } });\n    if (!episode) throw new Error(\"not-found\");\n    const data = sceneSchema.parse(await req.json());\n    const scene = await prisma.scene.create({ data: { ...data, episodeId: id } });\n    return NextResponse.json({ scene }, { status: 201 });\n  } catch (e) { return jsonError(e); }\n}\n\n=== api/fractions/[id]/retry/route.ts\nimport { NextRequest, NextResponse } from \"next/server\";\nimport { prisma } from \"@/lib/prisma\";\nimport { requireUser, jsonError } from \"@/lib/http\";\nimport { enqueueJob } from \"@/jobs/queue\";\ntype Ctx = { params: Promise<{ id: string }> };\nexport async function POST(req: NextRequest, ctx: Ctx) {\n  try {\n    const uid = await requireUser(req); const { id } = await ctx.params;\n    const fraction = await prisma.fraction.findFirst({\n      where: { id, scene: { episode: { season: { project: { ownerId: uid } } } } }\n    });\n    if (!fraction) throw new Error(\"not-found\");\n    const job = await enqueueJob({ type: \"EDIT_FRACTION\", fractionId: id, payload: { fractionId: id } });\n    await prisma.fraction.update({ where: { id }, data: { status: \"PENDING\" } });\n    return NextResponse.json({ job }, { status: 202 });\n  } catch (e) { return jsonError(e); }\n}\n\n=== api/fractions/[id]/route.ts\nimport { NextRequest, NextResponse } from \"next/server\";\nimport { prisma } from \"@/lib/prisma\";\nimport { requireUser, jsonError } from \"@/lib/http\";\nimport { fractionSchema } from \"@/lib/schemas\";\ntype Ctx = { params: Promise<{ id: string }> };\nexport async function PATCH(req: NextRequest, ctx: Ctx) {\n  try {\n    const uid = await requireUser(req); const { id } = await ctx.params;\n    const current = await prisma.fraction.findFirst({ where: { id, scene: { episode: { season: { project: { ownerId: uid } } } } } });\n    if (!current) throw new Error(\"not-found\");\n    const data = fractionSchema.partial().parse(await req.json());\n    const fraction = await prisma.fraction.update({ where: { id }, data: { ...data, version: { increment: 1 } } });\n    return NextResponse.json({ fraction });\n  } catch (e) { return jsonError(e); }\n}\nexport async function DELETE(req: NextRequest, ctx: Ctx) {\n  try { const uid = await requireUser(req); const { id } = await ctx.params;\n    const result = await prisma.fraction.deleteMany({ where: { id, scene: { episode: { season: { project: { ownerId: uid } } } } } });\n    if (!result.count) throw new Error(\"not-found\");\n    return NextResponse.json({ ok: true });\n  } catch (e) { return jsonError(e); }\n}\n\n=== api/jobs/[id]/retry/route.ts\nimport { NextRequest, NextResponse } from \"next/server\";\nimport { prisma } from \"@/lib/prisma\";\nimport { requireUser, jsonError } from \"@/lib/http\";\ntype Ctx = { params: Promise<{ id: string }> };\nexport async function POST(req: NextRequest, ctx: Ctx) {\n  try {\n    const uid = await requireUser(req); const { id } = await ctx.params;\n    const job = await prisma.job.findFirst({\n      where: { id, OR: [{ episode: { season: { project: { ownerId: uid } } } }, { fraction: { scene: { episode: { season: { project: { ownerId: uid } } } } } }] }\n    });\n    if (!job) throw new Error(\"not-found\");\n    if (job.status === \"RUNNING\") throw new Error(\"conflict\");\n    await prisma.job.update({ where: { id }, data: { status: \"QUEUED\", attempts: 0, progress: 0, error: null, startedAt: null, finishedAt: null, lockedAt: null } });\n    return NextResponse.json({ queued: true, jobId: id }, { status: 202 });\n  } catch (e) { return jsonError(e); }\n}\n\n=== api/jobs/[id]/route.ts\nimport { NextRequest, NextResponse } from \"next/server\";\nimport { prisma } from \"@/lib/prisma\";\nimport { requireUser, jsonError } from \"@/lib/http\";\ntype Ctx = { params: Promise<{ id: string }> };\nexport async function GET(req: NextRequest, ctx: Ctx) {\n  try {\n    const uid = await requireUser(req); const { id } = await ctx.params;\n    const job = await prisma.job.findFirst({\n      where: { id, OR: [{ episode: { season: { project: { ownerId: uid } } } }, { fraction: { scene: { episode: { season: { project: { ownerId: uid } } } } } }] }\n    });\n    if (!job) throw new Error(\"not-found\");\n    return NextResponse.json({ job });\n  } catch (e) { return jsonError(e); }\n}\n\n=== api/jobs/route.ts\nimport { NextRequest, NextResponse } from \"next/server\";\nimport { prisma } from \"@/lib/prisma\";\nimport { requireUser, jsonError } from \"@/lib/http\";\nimport { jobSchema } from \"@/lib/schemas\";\nimport { enqueueJob } from \"@/jobs/queue\";\nexport async function GET(req: NextRequest) {\n  try {\n    const uid = await requireUser(req);\n    const jobs = await prisma.job.findMany({\n      where: { OR: [{ episode: { season: { project: { ownerId: uid } } } }, { fraction: { scene: { episode: { season: { project: { ownerId: uid } } } } } }] },\n      orderBy: { createdAt: \"desc\" }, take: 100\n    });\n    return NextResponse.json({ jobs });\n  } catch (e) { return jsonError(e); }\n}\nexport async function POST(req: NextRequest) {\n  try {\n    const uid = await requireUser(req);\n    const input = jobSchema.parse(await req.json());\n    if (input.episodeId) {\n      const episode = await prisma.episode.findFirst({ where: { id: input.episodeId, season: { project: { ownerId: uid } } } });\n      if (!episode) throw new Error(\"not-found\");\n    }\n    if (input.fractionId) {\n      const fraction = await prisma.fraction.findFirst({ where: { id: input.fractionId, scene: { episode: { season: { project: { ownerId: uid } } } } } });\n      if (!fraction) throw new Error(\"not-found\");\n    }\n    const job = await enqueueJob({ type: input.type, episodeId: input.episodeId, fractionId: input.fractionId, payload: { ...input.payload, fractionId: input.fractionId } });\n    return NextResponse.json({ job }, { status: 202 });\n  } catch (e) { return jsonError(e); }\n}\n\n=== api/projects/[id]/route.ts\nimport { NextRequest, NextResponse } from \"next/server\";\nimport { prisma } from \"@/lib/prisma\";\nimport { requireUser, jsonError } from \"@/lib/http\";\nimport { projectSchema } from \"@/lib/schemas\";\ntype Ctx = { params: Promise<{ id: string }> };\n\nexport async function GET(req: NextRequest, ctx: Ctx) {\n  try {\n    const userId = await requireUser(req); const { id } = await ctx.params;\n    const project = await prisma.project.findFirst({ where: { id, ownerId: userId }, include: { seasons: { orderBy: { number: \"asc\" }, include: { episodes: { orderBy: { number: \"asc\" }, include: { scenes: { orderBy: { number: \"asc\" }, include: { fractions: { orderBy: { number: \"asc\" } } } } } } } } } });\n    if (!project) throw new Error(\"not-found\");\n    return NextResponse.json({ project });\n  } catch (e) { return jsonError(e); }\n}\nexport async function PATCH(req: NextRequest, ctx: Ctx) {\n  try {\n    const userId = await requireUser(req); const { id } = await ctx.params;\n    const data = projectSchema.partial().parse(await req.json());\n    const found = await prisma.project.findFirst({ where: { id, ownerId: userId } });\n    if (!found) throw new Error(\"not-found\");\n    const project = await prisma.project.update({ where: { id }, data });\n    return NextResponse.json({ project });\n  } catch (e) { return jsonError(e); }\n}\nexport async function DELETE(req: NextRequest, ctx: Ctx) {\n  try {\n    const userId = await requireUser(req); const { id } = await ctx.params;\n    const result = await prisma.project.deleteMany({ where: { id, ownerId: userId } });\n    if (!result.count) throw new Error(\"not-found\");\n    return NextResponse.json({ ok: true });\n  } catch (e) { return jsonError(e); }\n}\n\n=== api/projects/[id]/seasons/route.ts\nimport { NextRequest, NextResponse } from \"next/server\";\nimport { prisma } from \"@/lib/prisma\";\nimport { requireUser, jsonError } from \"@/lib/http\";\nimport { ownedProject } from \"@/lib/ownership\";\nimport { seasonSchema } from \"@/lib/schemas\";\ntype Ctx = { params: Promise<{ id: string }> };\nexport async function GET(req: NextRequest, ctx: Ctx) {\n  try { const uid = await requireUser(req); const { id } = await ctx.params; await ownedProject(id, uid);\n    const seasons = await prisma.season.findMany({ where: { projectId: id }, orderBy: { number: \"asc\" } });\n    return NextResponse.json({ seasons });\n  } catch (e) { return jsonError(e); }\n}\nexport async function POST(req: NextRequest, ctx: Ctx) {\n  try { const uid = await requireUser(req); const { id } = await ctx.params; await ownedProject(id, uid);\n    const data = seasonSchema.parse(await req.json());\n    const season = await prisma.season.create({ data: { ...data, projectId: id } });\n    return NextResponse.json({ season }, { status: 201 });\n  } catch (e) { return jsonError(e); }\n}\n\n=== api/projects/route.ts\nimport { NextRequest, NextResponse } from \"next/server\";\nimport { prisma } from \"@/lib/prisma\";\nimport { requireUser, jsonError } from \"@/lib/http\";\nimport { projectSchema } from \"@/lib/schemas\";\n\nexport async function GET(req: NextRequest) {\n  try {\n    const userId = await requireUser(req);\n    const projects = await prisma.project.findMany({ where: { ownerId: userId }, orderBy: { updatedAt: \"desc\" } });\n    return NextResponse.json({ projects });\n  } catch (e) { return jsonError(e); }\n}\nexport async function POST(req: NextRequest) {\n  try {\n    const userId = await requireUser(req);\n    const data = projectSchema.parse(await req.json());\n    const project = await prisma.project.create({ data: { ...data, ownerId: userId } });\n    return NextResponse.json({ project }, { status: 201 });\n  } catch (e) { return jsonError(e); }\n}\n\n=== api/scenes/[id]/fractions/route.ts\nimport { NextRequest, NextResponse } from \"next/server\";\nimport { prisma } from \"@/lib/prisma\";\nimport { requireUser, jsonError } from \"@/lib/http\";\nimport { fractionSchema } from \"@/lib/schemas\";\ntype Ctx = { params: Promise<{ id: string }> };\nexport async function GET(req: NextRequest, ctx: Ctx) {\n  try { const uid = await requireUser(req); const { id } = await ctx.params;\n    const scene = await prisma.scene.findFirst({ where: { id, episode: { season: { project: { ownerId: uid } } } } });\n    if (!scene) throw new Error(\"not-found\");\n    const fractions = await prisma.fraction.findMany({ where: { sceneId: id }, orderBy: { number: \"asc\" } });\n    return NextResponse.json({ fractions });\n  } catch (e) { return jsonError(e); }\n}\nexport async function POST(req: NextRequest, ctx: Ctx) {\n  try { const uid = await requireUser(req); const { id } = await ctx.params;\n    const scene = await prisma.scene.findFirst({ where: { id, episode: { season: { project: { ownerId: uid } } } } });\n    if (!scene) throw new Error(\"not-found\");\n    const data = fractionSchema.parse(await req.json());\n    const fraction = await prisma.fraction.create({ data: { ...data, sceneId: id } });\n    return NextResponse.json({ fraction }, { status: 201 });\n  } catch (e) { return jsonError(e); }\n}\n\n=== api/seasons/[id]/episodes/route.ts\nimport { NextRequest, NextResponse } from \"next/server\";\nimport { prisma } from \"@/lib/prisma\";\nimport { requireUser, jsonError } from \"@/lib/http\";\nimport { episodeSchema } from \"@/lib/schemas\";\ntype Ctx = { params: Promise<{ id: string }> };\nexport async function GET(req: NextRequest, ctx: Ctx) {\n  try { const uid = await requireUser(req); const { id } = await ctx.params;\n    const season = await prisma.season.findFirst({ where: { id, project: { ownerId: uid } } });\n    if (!season) throw new Error(\"not-found\");\n    const episodes = await prisma.episode.findMany({ where: { seasonId: id }, orderBy: { number: \"asc\" } });\n    return NextResponse.json({ episodes });\n  } catch (e) { return jsonError(e); }\n}\nexport async function POST(req: NextRequest, ctx: Ctx) {\n  try { const uid = await requireUser(req); const { id } = await ctx.params;\n    const season = await prisma.season.findFirst({ where: { id, project: { ownerId: uid } } });\n    if (!season) throw new Error(\"not-found\");\n    const data = episodeSchema.parse(await req.json());\n    const episode = await prisma.episode.create({ data: { ...data, seasonId: id } });\n    return NextResponse.json({ episode }, { status: 201 });\n  } catch (e) { return jsonError(e); }\n}\n\n","stderr":""}input.fractionIdhttps://github.com/duixcom/Duix-Avatarhttps://github.com/sbellybindletits429-dev/Duix-Avatarhttps://github.com/Anil-matcha/Open-Generative-AIcd /home/claude/ai-episode-studio/apps/mobile/app && cat > index.tsx <<'EOF'
import { useCallback, useEffect, useState } from "react";
import { View, Text, FlatList, Alert, RefreshControl } from "react-native";
import { router } from "expo-router";
import { api, friendly, isUnauthorized, post, signOut } from "@/lib/api";
import { Button, Field, Panel, Loading, colors } from "@/components/ui";

type Project = { id: string; title: string; description: string; updatedAt: string };
export default function Dashboard() {
  const [projects, setProjects] = useState<Project[]>([]);
  const [title, setTitle] = useState("");
  const [busy, setBusy] = useState(true);
  const load = useCallback(async () => {
    try { setProjects((await api<{ projects: Project[] }>("/projects")).projects); }
    catch (e) { if (isUnauthorized(e)) router.replace("/login"); else Alert.alert("Could not load projects", friendly(e)); }
    finally { setBusy(false); }
  }, []);
  useEffect(() => { load(); }, [load]);
  async function create() {
    if (!title.trim()) return;
    try { const r = await post<{ project: Project }>("/projects", { title }); setTitle(""); setProjects(p => [r.project, ...p]); }
    catch (e) { Alert.alert("Could not create project", friendly(e)); }
  }
  if (busy) return <Loading />;
  return <View style={{ flex: 1, backgroundColor: colors.bg, padding: 18 }}>
    <Text style={{ color: colors.text, fontSize: 28, fontWeight: "900", marginVertical: 12 }}>Your studio</Text>
    <Text style={{ color: colors.muted, marginBottom: 10 }}>Create and develop episodic video projects.</Text>
    <Field placeholder="New project title" value={title} onChangeText={setTitle} />
    <Button title="＋ Create project" onPress={create} />
    <FlatList data={projects} keyExtractor={p => p.id} refreshControl={<RefreshControl refreshing={false} onRefresh={load} tintColor={colors.accent} />}
      ListEmptyComponent={<Text style={{ color: colors.muted, marginTop: 30 }}>No projects yet. Create your first episode universe above.</Text>}
      renderItem={({ item }) => <Panel><Text onPress={() => router.push(`/project/${item.id}`)} style={{ color: colors.text, fontSize: 18, fontWeight: "800" }}>{item.title}</Text><Text style={{ color: colors.muted, marginTop: 5 }}>{item.description || "No description"}</Text></Panel>} />
    <Button tone="ghost" title="Sign out" onPress={async () => { await signOut(); router.replace("/login"); }} />
  </View>;
}
EOF
cat > "project/[id]/index.tsx" <<'EOF'
import { useCallback, useEffect, useState } from "react";
import { View, Text, ScrollView, Alert, RefreshControl } from "react-native";
import { router, useLocalSearchParams } from "expo-router";
import { api, friendly, patch, post } from "@/lib/api";
import { Button, Chip, Field, Muted, Panel, ProgressBar, Loading, Title, colors } from "@/components/ui";
import type { Aspect } from "@/lib/types";

type Episode = { id: string; number: number; title: string; scenes: { fractions: { status: string }[] }[] };
type Project = {
  id: string; title: string; description: string; visualStyle: string; stylePromptMod: string; directorInstructions: string; directorPromptMod: string; aspectRatio: Aspect;
  seasons: { id: string; number: number; title: string; episodes: Episode[] }[];
};
const mb = (bytes: number) => `${(bytes / 1048576).toFixed(1)} MB`;

export default function ProjectDetail() {
  const { id } = useLocalSearchParams<{ id: string }>();
  const [project, setProject] = useState<Project | null>(null);
  const [form, setForm] = useState({ visualStyle: "", stylePromptMod: "", directorInstructions: "", directorPromptMod: "", aspectRatio: "16:9" as Aspect });
  const [usage, setUsage] = useState<{ assets: number; bytes: number } | null>(null);
  const [seasonTitle, setSeasonTitle] = useState("Season 1");
  const [episodeTitle, setEpisodeTitle] = useState("Episode 1");
  const [dirty, setDirty] = useState(false);

  const load = useCallback(async () => {
    try {
      const r = await api<{ project: Project }>(`/projects/${id}`);
      setProject(r.project);
      setForm(f => dirty ? f : { visualStyle: r.project.visualStyle, stylePromptMod: r.project.stylePromptMod, directorInstructions: r.project.directorInstructions, directorPromptMod: r.project.directorPromptMod, aspectRatio: r.project.aspectRatio });
      setUsage(await api(`/projects/${id}/usage`));
    } catch (e) { Alert.alert("Load failed", friendly(e)); }
  }, [id, dirty]);
  useEffect(() => { load(); }, [id]);
  const edit = (patchValue: Partial<typeof form>) => { setForm(f => ({ ...f, ...patchValue })); setDirty(true); };

  async function save() {
    try { await patch(`/projects/${id}`, form); setDirty(false); Alert.alert("Saved", "Visual direction updated. It applies to shots you generate from now on."); }
    catch (e) { Alert.alert("Could not save", friendly(e)); }
  }
  async function addSeason() {
    try { await post(`/projects/${id}/seasons`, { title: seasonTitle, number: (project?.seasons.length ?? 0) + 1 }); await load(); }
    catch (e) { Alert.alert("Season error", friendly(e)); }
  }
  async function addEpisode(seasonId: string, number: number) {
    try { await post(`/seasons/${seasonId}/episodes`, { title: episodeTitle, number }); await load(); }
    catch (e) { Alert.alert("Episode error", friendly(e)); }
  }
  if (!project) return <Loading />;
  return <ScrollView style={{ flex: 1, backgroundColor: colors.bg }} contentContainerStyle={{ padding: 16, paddingBottom: 60 }} refreshControl={<RefreshControl refreshing={false} onRefresh={load} tintColor={colors.accent} />}>
    <Text style={{ color: colors.text, fontSize: 26, fontWeight: "900" }}>{project.title}</Text>
    {usage ? <Muted style={{ marginBottom: 10 }}>{usage.assets} stored files · {mb(usage.bytes)}</Muted> : null}
    <Button title="Characters & locations" onPress={() => router.push(`/project/${id}/library`)} />

    <Panel>
      <Title>Visual direction</Title>
      <Muted>Applied to every generated shot, keyframe and reference image.</Muted>
      <Field placeholder="Visual style (e.g. 35mm film, muted teal palette)" multiline value={form.visualStyle} onChangeText={v => edit({ visualStyle: v })} />
      <Field placeholder="Style modifiers" multiline value={form.stylePromptMod} onChangeText={v => edit({ stylePromptMod: v })} />
      <Field placeholder="Director instructions (camera, pacing, tone)" multiline value={form.directorInstructions} onChangeText={v => edit({ directorInstructions: v })} />
      <Field placeholder="Director modifiers" multiline value={form.directorPromptMod} onChangeText={v => edit({ directorPromptMod: v })} />
      <View style={{ flexDirection: "row", marginTop: 6, alignItems: "center" }}>
        <Muted style={{ marginRight: 8 }}>Format</Muted>
        {(["16:9", "9:16", "1:1"] as Aspect[]).map(a => <Chip key={a} label={a} active={form.aspectRatio === a} onPress={() => edit({ aspectRatio: a })} />)}
      </View>
      <Button title={dirty ? "Save changes" : "Saved"} disabled={!dirty} onPress={save} />
    </Panel>

    <Field value={seasonTitle} onChangeText={setSeasonTitle} placeholder="Season title" />
    <Button tone="ghost" title="＋ Add season" onPress={addSeason} />
    {project.seasons.map(season => <Panel key={season.id}>
      <Text style={{ color: colors.text, fontSize: 20, fontWeight: "800" }}>{season.title}</Text>
      {season.episodes.map(ep => {
        const shots = ep.scenes.flatMap(s => s.fractions); const done = shots.filter(f => f.status === "DONE").length;
        return <View key={ep.id} style={{ borderTopWidth: 1, borderColor: colors.border, paddingTop: 10, marginTop: 10 }}>
          <Text onPress={() => router.push(`/episode/${ep.id}`)} style={{ color: colors.text, fontWeight: "800", fontSize: 16 }}>{ep.number}. {ep.title}  ›</Text>
          <Muted>{ep.scenes.length} scenes · {done}/{shots.length} shots generated</Muted>
          <ProgressBar value={shots.length ? (done / shots.length) * 100 : 0} color={colors.green} />
        </View>;
      })}
      <Field value={episodeTitle} onChangeText={setEpisodeTitle} placeholder="Episode title" />
      <Button tone="ghost" title="＋ Add episode" onPress={() => addEpisode(season.id, season.episodes.length + 1)} />
    </Panel>)}
  </ScrollView>;
}
EOF
cat > "project/[id]/library.tsx" <<'EOF'
import { useCallback, useEffect, useState } from "react";
import { View, Text, ScrollView, Alert, Pressable } from "react-native";
import { useLocalSearchParams } from "expo-router";
import * as ImagePicker from "expo-image-picker";
import { api, del, friendly, patch, post, upload, waitForJob } from "@/lib/api";
import { Button, Chip, Field, Muted, Panel, Loading, Title, colors, confirm } from "@/components/ui";
import { Thumb } from "@/components/Media";
import { useAssetUrls, useBusy } from "@/lib/hooks";
import type { Character, Location } from "@/lib/types";

type Kind = "character" | "location";
type Item = Character | Location;

function ItemCard({ kind, item, projectId, onChanged }: { kind: Kind; item: Item; projectId: string; onChanged: () => void }) {
  const [name, setName] = useState(item.name);
  const [description, setDescription] = useState(item.description);
  const [voiceId, setVoiceId] = useState((item as Character).voiceId ?? "");
  const urls = useAssetUrls(item.referenceKeys);
  const { busy, run } = useBusy();
  const dirty = name !== item.name || description !== item.description || (kind === "character" && voiceId !== (item as Character).voiceId);
  const path = `/${kind === "character" ? "characters" : "locations"}/${item.id}`;
  const fail = (title: string) => (e: unknown) => Alert.alert(title, friendly(e));

  const save = () => run("save", async () => { await patch(path, { name, description, ...(kind === "character" ? { voiceId } : {}) }); onChanged(); }, fail("Could not save"));
  const addImage = () => run("upload", async () => {
    const picked = await ImagePicker.launchImageLibraryAsync({ mediaTypes: ["images"], quality: 0.9 });
    if (picked.canceled) return;
    const a = picked.assets[0];
    const file = await upload(projectId, { uri: a.uri, name: a.fileName ?? "reference.jpg", mimeType: a.mimeType ?? "image/jpeg" });
    await patch(path, { referenceKeys: [...item.referenceKeys, file.key] }); onChanged();
  }, fail("Upload failed"));
  const generate = () => run("generate", async () => {
    const { job } = await post<{ job: { id: string } }>("/jobs", { type: "GENERATE_REFERENCE", [kind === "character" ? "characterId" : "locationId"]: item.id });
    await waitForJob(job.id); onChanged();
  }, fail("Could not generate reference"));
  const removeImage = async (key: string) => { try { await patch(path, { referenceKeys: item.referenceKeys.filter(k => k !== key) }); onChanged(); } catch (e) { fail("Could not remove")(e); } };
  const remove = async () => { if (await confirm(`Delete ${item.name}?`, "Shots that use it keep their prompts but lose the link.", "Delete")) { try { await del(path); onChanged(); } catch (e) { fail("Could not delete")(e); } } };

  return <Panel>
    <Field value={name} onChangeText={setName} placeholder="Name" style={{ fontWeight: "800" }} />
    <Field value={description} onChangeText={setDescription} multiline placeholder={kind === "character" ? "Appearance: age, build, hair, clothing, distinguishing marks" : "Look and feel: architecture, light, time of day, mood"} />
    {kind === "character" ? <Field value={voiceId} onChangeText={setVoiceId} autoCapitalize="none" placeholder="Voice id (provider voice name, blank = default)" /> : null}
    <Muted>Reference images ({item.referenceKeys.length}/8) keep this {kind} consistent in every shot.</Muted>
    <ScrollView horizontal style={{ marginVertical: 8 }}>
      {item.referenceKeys.map(k => <Pressable key={k} onLongPress={() => removeImage(k)}><Thumb url={urls[k]} size={96} caption="hold to remove" /></Pressable>)}
      {!item.referenceKeys.length ? <Muted>No references yet. Upload or generate one.</Muted> : null}
    </ScrollView>
    <View style={{ flexDirection: "row", flexWrap: "wrap" }}>
      <Chip label={busy === "upload" ? "Uploading…" : "＋ Upload image"} onPress={busy ? undefined : addImage} />
      <Chip label={busy === "generate" ? "Generating…" : "✨ Generate reference"} onPress={busy ? undefined : generate} color={colors.blue} />
    </View>
    <Button title={dirty ? "Save changes" : "Saved"} disabled={!dirty || !!busy} onPress={save} />
    <Button tone="danger" title={`Delete ${kind}`} onPress={remove} />
  </Panel>;
}

function Library({ kind, projectId }: { kind: Kind; projectId: string }) {
  const plural = kind === "character" ? "characters" : "locations";
  const [items, setItems] = useState<Item[] | null>(null);
  const [name, setName] = useState("");
  const load = useCallback(async () => { try { setItems((await api<Record<string, Item[]>>(`/projects/${projectId}/${plural}`))[plural]); } catch (e) { Alert.alert("Load failed", friendly(e)); } }, [projectId, plural]);
  useEffect(() => { load(); }, [load]);
  async function add() {
    if (!name.trim()) return;
    try { await post(`/projects/${projectId}/${plural}`, { name }); setName(""); await load(); } catch (e) { Alert.alert("Could not add", friendly(e)); }
  }
  if (!items) return <Loading />;
  return <View>
    <Field value={name} onChangeText={setName} placeholder={kind === "character" ? "New character name" : "New location name"} />
    <Button title={`＋ Add ${kind}`} onPress={add} />
    {items.map(item => <ItemCard key={item.id + item.name} kind={kind} item={item} projectId={projectId} onChanged={load} />)}
  </View>;
}

export default function LibraryScreen() {
  const { id } = useLocalSearchParams<{ id: string }>();
  const [tab, setTab] = useState<Kind>("character");
  return <ScrollView style={{ flex: 1, backgroundColor: colors.bg }} contentContainerStyle={{ padding: 16, paddingBottom: 80 }} keyboardShouldPersistTaps="handled">
    <Title>Reference library</Title>
    <Muted style={{ marginBottom: 8 }}>Characters and locations are injected into every shot prompt, and their images are sent to the image model as references.</Muted>
    <View style={{ flexDirection: "row", marginBottom: 6 }}>
      <Chip label="Characters" active={tab === "character"} onPress={() => setTab("character")} />
      <Chip label="Locations" active={tab === "location"} onPress={() => setTab("location")} />
    </View>
    <Library key={tab} kind={tab} projectId={id} />
  </ScrollView>;
}
EOF
echo okindex.tsxr.project.aspectRatiocolors.bgf.statusseason.episodes.lengthitem.namea.fileNameitem.descriptionitem.ida.mimeType
```

- Restart the Docker service:

```
sudo systemctl restart docker
```

#### **Install the server**

```
cd /deploy
docker-compose -f docker-compose-linux.yml up -d
```

#### **Install the client**

1. Directly download the Linux version of the [officially built installation package](https://github.com/duixcom/Duix.Avatar/releases).
2. Double click `Duix.Avatar-x.x.x.AppImage` to launch it. No installation is required.

Reminder: In the Ubuntu system, if you enter the desktop as the `root` user, directly double - clicking `Duix.Avatar - x.x.x.AppImage` may not work. You need to execute `./Duix.Avatar - x.x.x.AppImage --no - sandbox` in the command - line terminal. Adding the `--no - sandbox` parameter will do the trick.



## 4. Open APIs

We have opened APIs for model training and video synthesis. After Docker starts, several ports will be exposed locally, accessible through `http://127.0.0.1`.

For specific code, refer to:

- src/main/service/model.js
- src/main/service/video.js
- src/main/service/voice.js

### **Model Training**

1. Separate video into silent video + audio
2. Place audio in

    `D:\duix_avatar_data\voice\data` is agreed with the `guiji2025/fish-speech-ziming` service, can be modified in docker-compose

3. Call the

    Parameter example:Response example:**Record the response results as they will be needed for subsequent audio synthesis**

### **Audio Synthesis**

Interface: `http://127.0.0.1:18180/v1/invoke`

```
// Request parameters
{
  "speaker": "{uuid}", // A unique UUID
  "text": "xxxxxxxxxx", // Text content to synthesize
  "format": "wav", // Fixed parameter
  "topP": 0.7, // Fixed parameter
  "max_new_tokens": 1024, // Fixed parameter
  "chunk_length": 100, // Fixed parameter
  "repetition_penalty": 1.2, // Fixed parameter
  "temperature": 0.7, // Fixed parameter
  "need_asr": false, // Fixed parameter
  "streaming": false, // Fixed parameter
  "is_fixed_seed": 0, // Fixed parameter
  "is_norm": 0, // Fixed parameter
  "reference_audio": "{voice.asr_format_audio_url}", // Return value from previous "Model Training" step
  "reference_text": "{voice.reference_audio_text}" // Return value from previous "Model Training" step
}
```

### **Video Synthesis**

- Synthesis interface: `http://127.0.0.1:8383/easy/submit`

  ```
  // Request parameters
  {
    "audio_url": "{audioPath}", // Audio path
    "video_url": "{videoPath}", // Video path
    "code": "{uuid}", // Unique key
    "chaofen": 0, // Fixed value
    "watermark_switch": 0, // Fixed value
    "pn": 1 // Fixed value
  }
  ```

- Progress query: `http://127.0.0.1:8383/easy/query?code=${taskCode}`

GET request, the parameter `taskCode` is the `code` from the synthesis interface input above

### **Important Notice to Developer Partners**

we are now announcing two parallel service solutions:

| **Project**              | **Duix.Avatar Open Source Local Deployment**                      | **Digital Human/Clone Voice API Service**                    |
| ------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Usage                    | Open Source Local Deployment                                 | Rapid Clone API Service                                      |
| Recommended              | Technical Users                                              | Business Users                                               |
| Technical Threshold      | Developers with deep learning framework experience/pursuing deep customization/wishing to participate in community co-construction | Quick business integration/focus on upper-level application development/need enterprise-level SLA assurance for commercial scenarios |
| Hardware Requirements    | Need to purchase GPU server                                  | No need to purchase GPU server                               |
| Customization            | Can modify and extend the code according to your needs, fully controlling the software's functions and behavior | Cannot directly modify the source code, can only extend functions through API-provided interfaces, less flexible than open source projects |
| Technical Support        | Community Support                                            | Dynamic expansion support + professional technical response team |
| Maintenance Cost         | High maintenance cost                                        | Simple maintenance                                           |
| Lip Sync Effect          | Usable effect                                                | Stunning and higher definition effect                        |
| Commercial Authorization | Supports global free commercial use (enterprises with more than 100,000 users or annual revenue exceeding 10 million USD need to sign a commercial license agreement) | Commercial use allowed                                       |
| Iteration Speed          | Slow updates, bug fixes depend on the community              | Latest models/algorithms are prioritized, fast problem resolution |

We always adhere to the open source spirit, and the launch of the API service aims to provide a more complete solution matrix for developers with different needs. No matter which method you choose, you can always obtain technical support documents through [https://duix.com](https://duix.com/)



We look forward to working with you to promote the inclusive development of digital human technology!



You can chat with Duix.Avatar Digital Human on the official website: https://duix.com/

We also provide  APl at DUIX Platform: https://docs.duix.com/api-reference/api/Introduction

## 5. What's New

### **[Nvidia 50 Series GPU Version Notice]**

1. Tested and verified on 5090 GPU
2. For installation instructions, see [Server Deployment Solution for NVIDIA 50 Series Graphics Cards](#Server-Deployment-Solution-for-NVIDIA-50-Series-Graphics-Cards)

### **[New Ubuntu Version Notice]**

**Ubuntu Version Officially Released**

1. Adaptation and verification work for Ubuntu 22.04 Desktop version (kernel 6.8.0-52-generic) has been completed. Compatibility testing for other Linux versions has not yet been conducted.
2. Added internationalization (English) for the client program interface.
3. Fixed some known issues
   - \#304
   - \#292
4. [Ubuntu22.04 Installation Documentation](https://github.com/duixcom/Duix.Avatar?tab=readme-ov-file#ubuntu-2204-installation)

## 6. FAQ

### **Self-Check Steps Before Asking Questions**

1. Check if all three services are in Running status

    ![img](README.assets/9.png)

2. Confirm that your machine has an NVIDIA graphics card and drivers are correctly installed.

All computing power for this project is local. The three services won't start without an NVIDIA graphics card or proper drivers.

3. Ensure both server and client are updated to the latest version. The project is newly open-sourced, the community is very active, and updates are frequent. Your issue might have been resolved in a new version.
   - Server: Go to `/deploy` directory and re-execute `docker-compose up -d`
   - Client: `pull` code and re-`build`
4. [GitHub Issues](https://github.com/duixcom/Duix.Avatar/issues) are continuously updated, issues are being resolved and closed daily. Check frequently, your issue might already be resolved.

### **Question Template**

1. Problem Description

Describe the reproduction steps in detail, with screenshots if possible.

2. Provide Error Logs
    - How to get client logs:

      ![img](README.assets/4.jpeg)

    - Server logs:

      Find the key location, or click on our three Docker services, and "Copy" as shown below.

      ![img](./README.assets/15.png)

## 7. How to Interact in real time

Duix.Avatar's digital human realizes digital human cloning and non-real-time video synthesis.

If you want a digital human to support interaction, you can visit [duix.com](www.duix.com) to experience the free test.

## 8. Contact

If you have any questions, please raise an issue or contact us at james@duix.com

## 9. License

https://github.com/duixcom/Duix.Avatar/blob/main/LICENSE

## 10. Acknowledgments

- ASR based on fun-asr
- TTS based on fish-speech-ziming

## 11. Star History

[GitHub Star History](https://www.star-history.com/#duixcom/Duix.Avatar&Date)
