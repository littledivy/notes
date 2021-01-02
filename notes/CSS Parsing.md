---
title: CSS Parsing
created: '2020-12-30T12:19:30.255Z'
modified: '2020-12-30T12:24:18.380Z'
---

# CSS Parsing

## Lexer

Analyse source code and spit out tokens.

### Tokens

```golang
type TokenType int
const (
  TokenEof TokenType = iota
  TokenUnknown
  TokenRBrace 
  TokenLBrace
  TokenIdent
  TokenImport
  TokenDecl
)
```

```css
@import "
```
