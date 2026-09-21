# AI search crawlers and training crawlers are not the same thing

Every major AI vendor runs two different crawlers, and blocking them means two completely
different things.

One crawler builds the search index that the assistant reads when it answers a question.
Block that one and your site cannot be cited, no matter how good your content is.
The other crawler collects text for model training. Blocking it is a normal business
decision and it does not affect whether you get cited today.

**Search crawlers** — blocking these removes you from AI answers:
`OAI-SearchBot`, `ChatGPT-User`, `Claude-SearchBot`, `Claude-User`, `PerplexityBot`, `Perplexity-User`

**Training crawlers** — blocking these is fine:
`GPTBot`, `ClaudeBot`, `anthropic-ai`, `Google-Extended`, `Applebot-Extended`, `CCBot`, `Bytespider`

One note that catches people out: `Google-Extended` controls Gemini training only. It has no
effect on Google Search or on AI Overviews.

The full reference, including six rules that break naive robots.txt parsers, is published at
**https://bizpartnership.github.io/ai-search-crawlers/**

Check your own site:

```
curl -s https://yourdomain.com/robots.txt | grep -iA2 "OAI-SearchBot\|Claude-SearchBot\|PerplexityBot"
```

Maintained by the team behind [askChat Studio](https://askchat.studio/), which measures whether
AI assistants name a local business when customers ask for a recommendation. Corrections are
welcome through the issue tracker.
