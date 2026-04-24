# Impeccable — Phân tích & Hướng dẫn sử dụng

> **1 skill, 23 commands, 35 reference files** — Bộ skill thiết kế frontend toàn diện nhất hiện tại cho AI agents.

## Tổng quan

**Impeccable** (by Paul Bakaus) là bản nâng cấp mạnh mẽ của skill `frontend-design` (Anthropic). Nó dạy AI **thiết kế thực sự** thay vì tạo "AI slop" — với 23 commands chuyên biệt và bộ anti-pattern detector.

| Thông tin | Chi tiết |
|-----------|----------|
| **Source** | [github.com/pbakaus/impeccable](https://github.com/pbakaus/impeccable) |
| **Website** | [impeccable.style](https://impeccable.style/) |
| **License** | Apache 2.0 (hoàn toàn miễn phí) |
| **Stars** | 21k+ GitHub stars |
| **Hỗ trợ** | Cursor, Claude Code, Gemini CLI, Codex CLI, Antigravity, và 30+ agents khác |

## Đã cài đặt thành công

```
npx skills add pbakaus/impeccable --yes --agent antigravity
```

Kết quả: `.agents/skills/impeccable/` — chứa **51 files** bao gồm:
- `SKILL.md` — file chính (11KB)
- `reference/` — 35 files tham chiếu chi tiết cho từng command/concept
- `scripts/` — 15 files JS (CLI tools, live mode, detection engine)
- `agents/` — Agent config

## Cấu trúc cài đặt

```
.agents/skills/impeccable/
├── SKILL.md                        ← Entry point (11KB)
├── reference/                      ← 35 reference files
│   ├── brand.md                    ← Brand register rules
│   ├── product.md                  ← Product register rules  
│   ├── typography.md               ← Typography deep reference
│   ├── color-and-contrast.md       ← Color theory reference
│   ├── spatial-design.md           ← Spacing/layout reference
│   ├── motion-design.md            ← Animation reference
│   ├── cognitive-load.md           ← UX psychology
│   ├── interaction-design.md       ← Interaction patterns
│   ├── responsive-design.md        ← Responsive rules
│   ├── ux-writing.md               ← Copy writing guide
│   ├── heuristics-scoring.md       ← Nielsen's heuristics
│   ├── personas.md                 ← User persona templates
│   ├── audit.md                    ← /audit command
│   ├── polish.md                   ← /polish command
│   ├── critique.md                 ← /critique command
│   ├── ... (20+ command refs)
│   └── live.md                     ← /live command (38KB!)
├── scripts/                        ← Runtime scripts
│   ├── load-context.mjs            ← Context loader
│   ├── design-parser.mjs           ← DESIGN.md parser (26KB)
│   ├── live-server.mjs             ← Live iteration server
│   ├── live-browser.js             ← Browser integration (189KB!)
│   └── ... (11 more scripts)
└── agents/
    └── openai.yaml
```

## 23 Commands (Phân loại)

### 🏗️ Build
| Command | Mô tả |
|---------|--------|
| `craft [feature]` | Shape + build feature end-to-end |
| `shape [feature]` | Plan UX/UI trước khi code |
| `teach` | Tạo PRODUCT.md + DESIGN.md context |
| `document` | Generate DESIGN.md từ codebase |
| `extract [target]` | Pull tokens/components thành design system |

### 🔍 Evaluate
| Command | Mô tả |
|---------|--------|
| `critique [target]` | UX review + Nielsen heuristics scoring |
| `audit [target]` | Technical quality (a11y, perf, responsive) |

### ✨ Refine
| Command | Mô tả |
|---------|--------|
| `polish [target]` | Final quality pass trước ship |
| `bolder [target]` | Amplify design nhạt/an toàn |
| `quieter [target]` | Tone down design quá aggressive |
| `distill [target]` | Strip to essence, bỏ phức tạp |
| `harden [target]` | Production-ready: errors, i18n, edge cases |
| `onboard [target]` | First-run flows, empty states |

### 🎨 Enhance
| Command | Mô tả |
|---------|--------|
| `animate [target]` | Purposeful animations/motion |
| `colorize [target]` | Thêm color chiến lược |
| `typeset [target]` | Cải thiện typography |
| `layout [target]` | Fix spacing, rhythm, hierarchy |
| `delight [target]` | Thêm personality, memorable touches |
| `overdrive [target]` | Push past conventional limits |

### 🔧 Fix
| Command | Mô tả |
|---------|--------|
| `clarify [target]` | Cải thiện UX copy, labels, errors |
| `adapt [target]` | Responsive cho devices khác nhau |
| `optimize [target]` | Diagnose/fix UI performance |

### 🔄 Iterate
| Command | Mô tả |
|---------|--------|
| `live` | Visual variant mode trong browser |

## Triết lý thiết kế cốt lõi

### Shared Design Laws (luôn áp dụng)
- **Color**: Dùng OKLCH. Không `#000`/`#fff`. Chọn color strategy trước (Restrained → Committed → Full palette → Drenched)
- **Theme**: Viết scene sentence cụ thể trước khi chọn dark/light
- **Typography**: Body max 65-75ch. Hierarchy qua scale+weight (≥1.25 ratio)
- **Layout**: Vary spacing for rhythm. Cards chỉ khi thực sự cần
- **Motion**: Không animate layout properties. Ease-out exponential curves
- **Copy**: Mỗi từ phải earn chỗ đứng. Không em dashes

### Absolute Bans (cấm tuyệt đối)
- ❌ Side-stripe borders (border-left/right > 1px)
- ❌ Gradient text (background-clip: text)
- ❌ Glassmorphism as default
- ❌ Hero-metric template (SaaS cliché)
- ❌ Identical card grids
- ❌ Modal as first thought

### AI Slop Test
> "If someone could look at this interface and say 'AI made that' without doubt, it's failed."

### Category-Reflex Check
> "observability → dark blue", "healthcare → white + teal", "finance → navy + gold" — nếu đoán được palette từ tên category, đó là training-data reflex → phải rework.

## So sánh với skills đã thu thập

| Skill | Scope | Depth |
|-------|-------|-------|
| `frontend-design.md` (Claude) | General principles | Shallow (~2KB) |
| `figma-implement-design.md` (Figma) | Figma → Code workflow | Medium (~11KB) |
| `theme-factory.md` (Anthropic) | Color+font presets | Narrow (~5KB) |
| `brand-guidelines.md` (Anthropic) | Brand identity tokens | Narrow (~3KB) |
| `canvas-design.md` (Anthropic) | Visual art creation | Medium (~5KB) |
| **impeccable** (pbakaus) | **Full design system** | **Deep (~280KB total)** |

> **Impeccable lớn hơn tất cả skills khác cộng lại ~10 lần**, và bao phủ mọi khía cạnh từ typography đến motion đến UX writing.

## Cách hoạt động với Antigravity

Skill đã được cài vào `.agents/skills/impeccable/`. Khi bạn yêu cầu tác vụ thiết kế, AI sẽ:

1. Load `PRODUCT.md` + `DESIGN.md` context (nếu có)
2. Xác định register: **brand** hay **product**
3. Load reference tương ứng
4. Áp dụng shared design laws
5. Thực thi command cụ thể theo reference file

## Ghi chú quan trọng

- **Skill này KHÔNG chỉ là tài liệu** — nó có runtime scripts (live mode, detection engine)
- Nó tạo ra `PRODUCT.md` và `DESIGN.md` trong project — 2 file context giúp AI thiết kế on-brand
- Tương thích với [Google Stitch DESIGN.md format](https://stitch.withgoogle.com/docs/design-md/format/)
- Chrome extension riêng để detect anti-patterns
- CLI riêng (`npx impeccable detect src/`) cho CI/CD
