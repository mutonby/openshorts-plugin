# OpenShorts for Claude

OpenShorts turns a long video into short vertical clips for TikTok, Instagram
Reels and YouTube Shorts. Give Claude a YouTube link (or share a video file)
and OpenShorts finds the strongest moments, cuts them into 15 to 60 second
clips, reframes them to 9:16 so the speaker stays in shot, burns word-by-word
captions and writes a title for each one.

**No API key to copy.** You sign in to OpenShorts and approve access.

## Install

From the Claude directory, or in Claude Code:

```
/plugin install openshorts --marketplace mutonby/openshorts-plugin
```

## What you can do

- **Clip a video:** podcasts, interviews, webinars, talks, livestreams and
  tutorials. Choose how many clips and how long, or let the AI decide.
- **Pick the best:** list the clips with their titles and open each one.
- **Restyle captions:** karaoke, one word at a time or highlighted, with your
  font, size and colours.
- **Re-cut a clip:** trim it, extend it, drop a dead moment or join two moments.
- **Publish:** post a clip to your connected TikTok, Instagram and YouTube
  accounts now or schedule it for later. Nothing is posted unless you ask.

Try: "Make shorts from this podcast: <YouTube link>", "Give me 5 clips of 30
seconds from this interview", "Make the captions of clip 2 karaoke style" or
"Post clip 1 to TikTok tomorrow at 9am".

## What the plugin contains

- **MCP server** `https://mcp.openshorts.app/mcp` (OpenShorts' own hosted
  server). You sign in with your OpenShorts account through OAuth the first
  time Claude uses it. The plugin sends no credentials of its own and runs
  nothing on your machine.
- **Skill** `openshorts`: tells Claude the flow (submit, wait, list, edit,
  publish) and the rules (rights confirmation, publish only on request).

## Data and accounts

The video URL or file you give is processed on OpenShorts' servers to make the
clips. Processing uses minutes from your OpenShorts plan; new accounts get free
minutes. You must own the video or hold the rights to it. Publishing goes
through the social accounts you connected at openshorts.app.

- Website: https://www.openshorts.app
- Docs: https://www.openshorts.app/mcp
- Privacy policy: https://www.openshorts.app/privacy
- Terms: https://www.openshorts.app/terms
- Support: info@openshorts.app

## License

MIT. See [LICENSE](LICENSE).
