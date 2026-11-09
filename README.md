# Playtable MCP server

Make up any game and play it right in your chat.

Playtable is a hosted MCP server. Ask Claude, ChatGPT or another agent for a game ("let's play checkers", "make up a card game and deal me in") and a real board shows up in the chat. You click to move, the agent takes its turn, and friends can join empty seats from a link.

The server is the table. It keeps the board, deals the cards and keeps every hand hidden, and rolls the dice itself. The agent only ever sees its own seat, so it can't peek at your cards or fudge a roll. When it has to keep a secret, like the word in hangman, it locks it in at the start and it's revealed at the end.

This repository holds the listing files for MCP directories. The server itself is hosted, so there's nothing to install or run.

## Connect

Endpoint: `https://play.rowhousesoftware.com/mcp` (Streamable HTTP, no key needed)

```json
{
  "mcpServers": {
    "playtable": { "type": "http", "url": "https://play.rowhousesoftware.com/mcp" }
  }
}
```

In Claude: Customize, then Connectors, then Add custom connector, and paste the URL.

## Tools

| Tool | What it does |
|-|-|
| `create_game` | Set up a game from a description or a starter. Shows an interactive board in the chat (MCP Apps). |
| `get_state` | What the agent's seat can see: the board, its hand, scores, dice and the log. |
| `take_turn` | One or more moves for the agent's seat, all or nothing. |
| `show_board` | Show the board in the chat again. |

## What games

Anything built from a grid board with pieces, a deck with hidden hands and piles, dice, counters and committed secrets. Starters: tic-tac-toe, four in a row, gomoku, checkers, reversi, crazy eights, go fish, twenty-one, Pig, sea battle, hangman and twenty questions.

## Links

- Site: https://play.rowhousesoftware.com
- For developers: https://play.rowhousesoftware.com/guides/mcp-server-for-games
- Official MCP registry: `com.rowhousesoftware/playtable`
- Support: support@rowhousesoftware.com
