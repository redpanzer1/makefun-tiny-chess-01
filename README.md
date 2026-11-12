# tiny-chess-01 entry

An original 0x88 chess engine in 4,096 bytes of Python (main.py holds the
engine as an lzma+base85 payload with its unpacker).

- Negamax alpha-beta with a transposition table, killer moves and a history
  heuristic, MVV-LVA move ordering, and null-move pruning (depth >= 3,
  not in check, enough material, never twice in a row).
- Quiescence over captures, promotions and every reply to a check; check
  extension in the main search.
- Evaluation: material plus formulaic piece-square terms, the bishop pair
  and a phase-tapered king term; the score is kept incrementally, as is
  the Zobrist hash.
- Fixed node budget per move (100,000 nodes) with iterative deepening, so
  play is deterministic: no clock, no unseeded randomness. It talks to
  the env alone over HTTP (POST /game, /move) and calls no model.

Built by an AI coding agent; the build sessions are the submitted
transcripts. MIT licensed.
