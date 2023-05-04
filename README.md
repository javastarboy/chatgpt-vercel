# ChatGPT-API Demo

English | [简体中文](./README.zh-CN.md)

A demo repo based on [OpenAI GPT-3.5 Turbo API.](https://platform.openai.com/docs/guides/chat)

**🍿 Live preview**: https://www.javastarboy.cn

> ⚠️ Notice: Our API Key limit has been exhausted. So the demo site is not available now.

![chat-logo](https://cdn.staticaly.com/gh/yzh990918/static@master/chat-logo.webp)

## Running Locally

### Pre environment
1. **Node**: Check that both your development environment and deployment environment are using `Node v18` or later. You can use [nvm](https://github.com/nvm-sh/nvm) to manage multiple `node` versions locally。
   ```bash
    node -v
   ```
2. **PNPM**: We recommend using [pnpm](https://pnpm.io/) to manage dependencies. If you have never installed pnpm, you can install it with the following command:
   ```bash
    npm i -g pnpm
   ```
3. **OPENAI_API_KEY**: Before running this application, you need to obtain the API key from OpenAI. You can register the API key at [https://beta.openai.com/signup](https://beta.openai.com/signup).

### Getting Started

1. Install dependencies
   ```bash
    pnpm install
   ```
2. Copy the `.env.example` file, then rename it to `.env`, and add your [OpenAI API key](https://platform.openai.com/account/api-keys) to the `.env` file.
   ```bash
    OPENAI_API_KEY=sk-xxx...
   ```
3. Run the application, the local project runs on `http://localhost:3000/`
   ```bash
    pnpm run dev
   ```

## Deploy

### Deploy With Vercel

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/javastarboy/chatgpt-vercel&env=OPENAI_API_KEY&envDescription=OpenAI%20API%20Key&envLink=https://platform.openai.com/account/api-keys)

> #### 🔒 Need website password?
>
> Deploy with the [`SITE_PASSWORD`](#environment-variables)
>
> <a href="https://vercel.com/new/clone?repository-url=https://vercel.com/new/clone?repository-url=https://github.com/javastarboy/chatgpt-vercel&env=OPENAI_API_KEY&env=SITE_PASSWORD&envDescription=OpenAI API Key&envLink=https://platform.openai.com/account/api-keys" alt="Deploy with Vercel" target="_blank"><img src="https://vercel.com/button" alt="Deploy with Vercel" height=24 style="vertical-align: middle; margin-right: 4px;"></a>

![image](https://cdn.staticaly.com/gh/yzh990918/static@master/20230310/image.4wzfb79qt7k0.webp)


### Deploy With Netlify

[![Deploy with Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/javastarboy/chatgpt-vercel#OPENAI_API_KEY=&HTTPS_PROXY=&OPENAI_API_BASE_URL=&HEAD_SCRIPTS=&PUBLIC_SECRET_KEY=&OPENAI_API_MODEL=&SITE_PASSWORD=)

**Step-by-step deployment tutorial:**

1. [Fork](https://github.com/javastarboy/chatgpt-vercel/fork) this project，Go to [https://app.netlify.com/start](https://app.netlify.com/start) new Site, select the project you `forked` done, and connect it with your `GitHub` account.

![image](https://cdn.staticaly.com/gh/yzh990918/static@master/20230310/image.3nlt4hgzb16o.webp)

![image](https://cdn.staticaly.com/gh/yzh990918/static@master/20230310/image.5fhfouap270g.webp)


2. Select the branch you want to deploy, then configure environment variables in the project settings.

![image](https://cdn.staticaly.com/gh/yzh990918/static@master/20230311/image.gfs9lx8c854.webp)

3. Select the default build command and output directory, Click the `Deploy Site` button to start deploying the site。

![image](https://cdn.staticaly.com/gh/yzh990918/static@master/20230311/image.4jky9e1wbojk.webp)


### Deploy with Docker

Environment variables refer to the documentation below. [Docker Hub address](https://hub.docker.com/r/ddiu8081/chatgpt-demo).

**Direct run**
```bash
docker run --name=chatgpt-demo -e OPENAI_API_KEY=YOUR_OPEN_API_KEY -p 3000:3000 -d ddiu8081/chatgpt-demo:latest
```
`-e` define environment variables in the container.


**Docker compose**
```yml
version: '3'

services:
  chatgpt-demo:
    image: ddiu8081/chatgpt-demo:latest
    container_name: chatgpt-demo
    restart: always
    ports:
      - '3000:3000'
    environment:
      - OPENAI_API_KEY=YOUR_OPEN_API_KEY
      # - HTTPS_PROXY=YOUR_HTTPS_PROXY
      # - OPENAI_API_BASE_URL=YOUR_OPENAI_API_BASE_URL
      # - HEAD_SCRIPTS=YOUR_HEAD_SCRIPTS
      # - PUBLIC_SECRET_KEY=YOUR_SECRET_KEY
      # - SITE_PASSWORD=YOUR_SITE_PASSWORD
      # - OPENAI_API_MODEL=YOUR_OPENAI_API_MODEL
```

```bash
# start
docker compose up -d
# down
docker-compose down
```

### Deploy on more servers

Please refer to the official deployment documentation：https://docs.astro.build/en/guides/deploy

## Environment Variables

You can control the website through environment variables.

| Name | Description | Default |
| --- | --- | --- |
| `OPENAI_API_KEY` | Your API Key for OpenAI. | `null` |
| `HTTPS_PROXY` | Provide proxy for OpenAI API. e.g. `http://127.0.0.1:7890` | `null` |
| `OPENAI_API_BASE_URL` | Custom base url for OpenAI API. | `https://api.openai.com` |
| `HEAD_SCRIPTS` | Inject analytics or other scripts before `</head>` of the page | `null` |
| `PUBLIC_SECRET_KEY` | Secret string for the project. Use for generating signatures for API calls | `null` |
| `SITE_PASSWORD` | Set password for site, support multiple password separated by comma. If not set, site will be public | `null` |
| `OPENAI_API_MODEL` | ID of the model to use. [List models](https://platform.openai.com/docs/api-reference/models/list) | `gpt-3.5-turbo` |


# 交流社群
如果你觉得我的分享对比有帮助，也欢迎加入我们交流社群，每天都有很多关于 ChatGPT、人工智能 AI、Python、变现创业的相关分享。
<div style="text-align:center">
    <img src="https://github.com/javastarboy/WeChatGPT_JSB/blob/master/pictures/%E4%B8%93%E9%9D%A2%E5%90%91%E4%BA%8E%E6%8A%80%E6%9C%AF%E4%BA%BA%E5%91%98%E4%BC%98%E6%83%A0%E5%88%B8-GitHub.png">
</div>

# 赞助
***
如果你觉得这个项目对你有帮助，并且情况允许的话，可以给我一点点支持，总之非常感谢支持～

## 微信
<div style="text-align:center">
    <img src="https://github.com/javastarboy/WeChatGPT_JSB/blob/master/pictures/%E5%BE%AE%E4%BF%A1%E6%94%B6%E6%AC%BE%E7%A0%81.png">
</div>

## 支付宝
<div style="text-align:center">
    <img src="https://github.com/javastarboy/WeChatGPT_JSB/blob/master/pictures/%E6%94%AF%E4%BB%98%E5%AE%9D%E6%94%B6%E6%AC%BE%E7%A0%81.png">
</div>
