- Chào mừng đến với Thị Trấn Pixel

- Pixel Town là một game mô phỏng những cuộc trò chuyện của con người. Những nhân vật trong đó được training tính cách và sở thích khác nhau, nhờ OpenAI để có thể tạo các cuộc hội thoại mới. Cuộc hội thoại sẽ được bắt đầu khi 2 nhân vật đến gần nhau.

- Kéo và thả chuột để di chuyển quanh thị trấn, cuộn chuột vào và ra để thu phóng. Bạn có thể nhập vào nhân vật để xem lịch sử trò chuyện của họ.

## Stack

- Game engine, database, and vector search: [Convex](https://convex.dev/)
- Text model: [OpenAI](https://platform.openai.com/docs/models)
- Deployment: [Vercel](https://vercel.com/)
- Pixel Art Generation: [Replicate](https://replicate.com/), [Fal.ai](https://serverless.fal.ai/lora)
- Itch: [Itch](https://itch.io/)
- Tiled: [Tiled](https://www.mapeditor.org/)
- Music Generation: [Replicate](https://replicate.com/) using [MusicGen](https://huggingface.co/spaces/facebook/MusicGen)

## Installation

- `npm run dev` will fail asking for environment variables.
  Enter them in the environment variables on your Convex dashboard to proceed.
  You can get there via `npx convex dashboard` or https://dashboard.convex.dev
  See below on how to get the various environment variables.

a. **OpenAI API key**

Visit https://platform.openai.com/account/api-keys to get your OpenAI API key and set the
`OPENAI_API_KEY` environment variable in your Convex deployment (see below).

b. **Replicate API key (Optional)**
For Daily background music generation, create a
[Replicate](https://replicate.com/) account and create a token in your Profile's
[API Token page](https://replicate.com/account/api-tokens).
Add the token as `REPLICATE_API_TOKEN` in your Convex environment variables.

c. **Convex**
**To stop the back end, in case of too much activity**
This will stop running the engine and agents. You can still run queries and
run functions to debug.

```bash
npx convex run testing:stop
```

**To restart the back end after stopping it**

```bash
npx convex run testing:resume
```

**To archive the world**

```bash
npx convex run testing:archive
```

You can then create a fresh world with `init`.

```bash
npx convex run init
```

**To clear all databases**
You can wipe all tables with the `wipeAllTables` testing function.

```bash
npx convex run testing:wipeAllTables
```

#### Deploy to Vercel

- Register an account on Vercel and then [install the Vercel CLI](https://vercel.com/docs/cli).
- **If you are using Github Codespaces**: You will need to [install the Vercel CLI](https://vercel.com/docs/cli) and authenticate from your codespaces cli by running `vercel login`.
- Deploy the app to Vercel with `vercel --prod`.
