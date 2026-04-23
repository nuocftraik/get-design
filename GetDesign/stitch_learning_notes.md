# 📘 Ghi chú học Stitch — Tổng hợp 6 Lessons

---

## Lesson 1: Essentials — Nền tảng cơ bản

### Triết lý cốt lõi

> **Thiết kế tốt hơn đến từ ITERATION, không phải từ prompt hoàn hảo ngay lần đầu.**

Đừng overthink prompt đầu tiên. Mục tiêu là **vượt qua trang trắng** → vào được vòng lặp sáng tạo càng nhanh càng tốt.

### Công thức prompt khởi đầu

```
Idea    → Cái gì (landing page, app, dashboard...)
Theme   → Phong cách chung (modern, tối giản, high contrast...)
Content → Nội dung cụ thể trên trang (headline, sections, buttons...)
Image   → (Tuỳ chọn) Ảnh tham khảo
```

**Ví dụ thực tế:**
```
Idea:    Landing page cho podcast chạy bộ "The Pacing Project"
Theme:   Modern, edgy, high contrast. Đen trắng, góc cạnh.
Content: Hero section với headline "Stories and lessons about 
         racing and proper pacing", links đến podcast platforms.
```

### Device Type — Chọn App hay Web

Chỉ cần chọn nhanh theo cảm giác ban đầu. Stitch có cách chuyển đổi giữa App ↔ Web sau, nên đừng lo lắng quá ở bước này.

### Canvas — Điều hướng cơ bản

| Phím | Chức năng |
|---|---|
| `V` | Select tool — chọn và di chuyển screen |
| `H` | Pan tool — kéo canvas |
| `Ctrl+←` | Nhảy về screen gần nhất (khi bị lạc) |
| `Ctrl+→` / `Ctrl+←` | Chuyển giữa các screen |

### Quy trình ideation

Khi design đầu tiên xuất hiện → bắt đầu iterate:

1. **Sửa MỘT thứ mỗi lần** — Chọn screen → Edit → viết prompt cụ thể
2. **Dùng UI/UX keywords** — Prompt càng cụ thể, kết quả càng chính xác
3. **Edit Theme** — Muốn đổi style tổng thể (dark/light, accent color, font, corner radius) → dùng Edit Theme, nhanh hơn prompt tay

**Ví dụ prompt edit tốt:**
```
Target:    Pricing table
Action:    Emphasize the middle card
How:       Increase container height, add drop shadow, 
           reduce scale of sibling cards
Why:       Tạo visual hierarchy rõ ràng
```

### Prototype — Test drive design

Chọn screen → Generate → Prototype → Stitch tạo bản tương tác (scroll, hover, click, nhập text). Dùng để:
- Check hover styles của buttons, links, cards
- Test textbox có đủ lớn không
- Cảm nhận design "ngoài đời thật" thế nào

### Export — Lấy code và hình

- Chọn screen(s) → Download → Zip file chứa HTML + images
- HTML này là **base layer** — dùng LLM chuyển sang React, Angular, Vue, Flutter, SwiftUI, Jetpack Compose...

> [!TIP]
> HTML output của Stitch không phải production code. Nó là **design reference dưới dạng code** — dùng làm đầu vào để convert sang framework bạn cần.

---

## Lesson 2: Effective Prompting — Viết prompt hiệu quả

### Bắt đầu từ đâu?

Có 2 cách tiếp cận:

**High-Level (tổng quát):**
```
An app for marathon runners.
```

**Detailed (chi tiết):**
```
An app for marathon runners to engage with a community, 
find partners, get training advice, and find races near them.
```

→ App phức tạp? Bắt đầu high-level, rồi **drill down từng screen**.

### Set the Vibe — Dùng tính từ

Tính từ ảnh hưởng trực tiếp đến màu sắc, font, imagery:

```
"A vibrant and encouraging fitness tracking app"
→ Màu tươi sáng, font thân thiện, hình ảnh năng động

"A minimalist and focused app for meditation"  
→ Nhiều whitespace, font thanh lịch, tông trầm
```

### Iterate từng screen — Công thức prompt chuẩn

```
[Target cụ thể] + [Hành động cụ thể] + [UI/UX keyword]
```

**Ví dụ:**
```
Change the primary CTA button on the login screen 
to be larger and use the brand's primary blue color.
  ↑ target cụ thể        ↑ hành động cụ thể    ↑ brand reference
```

**Prompt cho từng loại screen:**
```
E-commerce: "Product detail page for a Japandi-styled tea store. 
Sells herbal teas, ceramics. Neutral, minimal colors, 
black buttons. Soft, elegant font."

Music app: "Music player page for 'Suburban Legends.' 
Album art is a macro photo of ocean water. 
Page background should reflect this."
```

### Điều khiển theme

| Muốn đổi | Cách prompt |
|---|---|
| **Màu cụ thể** | "Change primary color to forest green" |
| **Màu theo mood** | "Update theme to a warm, inviting color palette" |
| **Font** | "Use a playful sans-serif font" hoặc "Change headings to serif" |
| **Border/Button** | "Make all buttons have fully rounded corners" |
| **Kết hợp** | "Book discovery app: serif font, light green brand color for accents" |

### Sửa hình ảnh trong design

**Sửa tất cả:** `"Change background of all product images on landing page to light taupe"`

**Sửa cụ thể:**
```
Location:   On 'Team' page
Target:     Image of 'Dr. Carter (Lead Dentist)'
Action:     Update her lab coat to black
```

**Đồng bộ hình với theme:** `"Update theme to light orange. Ensure all images and icons match this new color scheme."`

### Đổi ngôn ngữ

```
"Switch all product copy and button text to Spanish."
```

### Pro Tips tóm gọn

- **Be Clear & Concise** — tránh mơ hồ
- **One Major Change at a Time** — dễ đánh giá kết quả
- **Use UI/UX Keywords** — "navigation bar", "CTA button", "card layout"
- **Reference Elements Specifically** — "primary button on sign-up form"
- **Không đúng → rephrase** — đổi cách diễn đạt hoặc target cụ thể hơn

---

## Lesson 3: Device Types — App vs Web

### Không chỉ là kích thước — mà là cách tư duy layout

| | App Mode | Web Mode |
|---|---|---|
| **Scroll** | Vertical | Horizontal sprawl |
| **Navigation** | Bottom tab bar (thumb zone) | Top navbar |
| **Layout** | Stacked, single column | Multi-column grid |
| **Hierarchy** | Content xếp chồng | Content trải rộng |

> [!IMPORTANT]
> Chuyển App ↔ Web là **TRANSLATE**, không phải **RESIZE**. Phải viết prompt giải thích cách tổ chức lại layout.

### Ví dụ translate: App Raffinato → Web

**Phase 1 — App Design:**
```
Idea:       Ordering app cho quán espresso "Raffinato"
Theme:      Light, high contrast, minimalistic
Content:    Variable grid (1 col → 2 col), sections categorized 
            by drink type, focus typography on item names
Navigation: Switch giữa main grid / details / cart
```

**Phase 2 — Translate sang Web:**
```
Navigation: Consolidate bottom tab + top menu → single horizontal 
            navbar at top (Home, Menu, Rewards, Account)

Hero:       Transform 'The Daily Focus' card → split-layout hero 
            (text + button bên trái, image full cover bên phải)

Grid:       Update 2-column mobile → 4-column desktop grid.
            Maintain light cream cards và minimalist vibe.
```

→ Prompt tập trung vào **Navigation**, **Hero**, **Grid Density** — 3 thứ khác biệt lớn nhất giữa mobile và desktop.

### Chuyển device type trong cùng project

Nếu generate Web prompt trong App project → Stitch tạo web content **trong app frame**:
1. Generate design
2. Dùng Preview → Device Type để chuyển view sang Desktop
3. Resize frame nếu bị cắt

> [!TIP]
> **Hidden Content:** Khi chuyển từ App → Web trong cùng project, hãy **kéo frame handle xuống thật nhiều**. Stitch thường generate đầy đủ layout nhưng ẩn phần dưới vì App frame quá ngắn. Kéo xuống sẽ lộ ra phần còn lại.

---

## Lesson 4: Design Modes — Chọn đúng engine

### Stitch không phải 1 AI model — mà là nhiều engine chuyên biệt

| Mode | Engine | Best for | Đặc điểm |
|---|---|---|---|
| **Thinking with 3 Pro** | Gemini 3 Pro | Dashboard phức tạp, landing page nhiều nuance, bản "production" | Chậm nhất nhưng **reasoning sâu** — nó "suy nghĩ" về flow, hierarchy, màu sắc tương tác |
| **Redesign** | Nano Banana Pro | Modernize app cũ, thay đổi phong cách, "vibe design" | Tốt nhất cho thí nghiệm visual |
| **2.5 Pro** | Gemini 2.5 Pro | HTML chất lượng cao, so sánh A/B | Code fidelity cực tốt |
| **Fast** | (optimized) | Wireframe nhanh, export Figma | Nhanh nhất, hy sinh chi tiết |

> [!TIP]
> **Trick hay:** Chạy cùng prompt trên **3 Pro** và **2.5 Pro** → so sánh 2 bản → chọn cái tốt hơn. Giống hỏi 2 designer cùng brief.

### Style Word Bank — Từ khoá dùng với Redesign mode

Redesign mode **phát huy tối đa** khi bạn dùng các keyword phong cách cụ thể thay vì nói "make it cool":

**Layout & Structure:**
| Keyword | Mô tả |
|---|---|
| **Bento Grid** | Card-based, boxy, modular — kiểu dashboard iOS widgets |
| **Editorial** | Magazine feel — serif lớn, whitespace nhiều, ảnh bất đối xứng |
| **Swiss Style** | Grid cứng, sans-serif (Helvetica), text flush-left, cực clean |
| **Split-Screen** | Chia dọc: một bên solid color, một bên full-bleed image |

**Texture & Depth:**
| Keyword | Mô tả |
|---|---|
| **Glassmorphism** | Kính mờ — translucency, blur, viền trắng mỏng |
| **Claymorphism** | 3D mềm, inner shadow, friendly — kiểu đất sét |
| **Skeuomorphic** | Texture thật (da, giấy, kim loại), nút bấm giống vật lý |
| **Grainy/Noise** | Film grain overlay, giảm "digital shine", thêm warmth |

**Atmosphere & Era:**
| Keyword | Mô tả |
|---|---|
| **Brutalist** | Thô, mộc, system font, high contrast — "ugly-cool" |
| **Cyberpunk** | Dark mode, neon cyan/magenta, glitch effects |
| **Y2K** | Late 90s — chrome, bubble letters, xanh hồng, pill buttons |
| **Retro-Futurism** | 80s Synthwave — sunset, wireframe grid, VHS, glowing lines |

**Color & Contrast:**
| Keyword | Mô tả |
|---|---|
| **Duotone** | Chỉ 2 màu đối lập (và shades của chúng) |
| **Monochromatic** | 1 màu base (vd: "Shades of Electric Blue") |
| **Pastel Goth** | Pastel mềm + typography đen cứng |
| **Dark Mode OLED** | True black (#000000), không phải dark grey |

**Ví dụ kết hợp:**
```
"Redesign this dashboard. Use a modern Bento Grid layout. 
Dark mode background. Use the Inter font for headers."
```

---

## Lesson 5: Variations — Khám phá nhiều hướng cùng lúc

### Khi nào dùng Variations?

| Tình huống | Dùng |
|---|---|
| Bị stuck — biết design chưa ổn nhưng không biết sửa gì | ✅ Variations |
| Muốn explore 3 layout khác nhau cho cùng nội dung | ✅ Variations |
| Muốn đổi toàn bộ vibe (Corporate → Cyberpunk) | ✅ Variations |
| Sửa cụ thể 1 chi tiết nhỏ (đổi màu nút) | ❌ Dùng Edit/Chat |

### Creative Range — Stitch đi xa bao nhiêu?

| Range | Hành vi | Khi nào dùng |
|---|---|---|
| **Refined (Low)** | Giữ structure, chỉ đổi font, spacing, màu | Polish, gần xong |
| **Creative (High)** | Tự do hoàn toàn — đổi layout, imagery, theme | Explore, đang tìm hướng |

### Prompt cho Variations ≠ Prompt cho Edit

Với Edit → **1 thay đổi/lần** (cụ thể).
Với Variations → **swing lớn được** (kết hợp theme + layout):

```
"Update the app theme to a luxury aesthetic using a strict 
black and white palette. On the Episode List screen, 
change the layout to a minimalist grid."
```

Nhưng vẫn phải **specific về hướng đi**:
```
❌ "Make it different"
✅ "Make it minimalist"
✅ "Make it bold"
```

### Kỹ thuật "Vary the Variation"

Đây là power move:

```
1. Generate 5 variations
2. Option 3 → layout đẹp nhất
   Option 5 → color scheme đẹp nhất
3. Chọn Option 3 làm base
4. Hạ Creative Range → Refined
5. Prompt: "Bring in the color scheme from the previous 
   variation with warm tones"
6. → Kết quả = Layout tốt nhất + Color tốt nhất
```

Bạn có thể **chạy variations trên variations** — lồng nhiều lớp cho đến khi ưng ý.

---

## Lesson 6: Controls & Hotkeys — Thao tác nhanh trên Canvas

### Shortcuts cốt lõi

**Edit Actions:**
| Shortcut | Chức năng |
|---|---|
| `Ctrl+Z` | Undo |
| `Ctrl+Shift+Z` | Redo |
| `Ctrl+C` / `Ctrl+V` | Copy / Paste |
| `Ctrl+D` | Duplicate screen |
| `Delete` / `Backspace` | Xoá |
| `Ctrl+A` | Select All |

**Canvas Tools:**
| Shortcut | Chức năng |
|---|---|
| `V` | Select — chọn, di chuyển screen (default) |
| `H` | Pan — kéo canvas |
| `Z` | Zoom — click zoom in, Alt+click zoom out, kéo chọn vùng |

**View Controls:**
| Shortcut | Chức năng |
|---|---|
| `+` / `Ctrl+=` | Zoom In |
| `-` / `Ctrl+-` | Zoom Out |
| `0` / `Ctrl+1` | Fit to View — zoom vừa toàn bộ content |

**Project Actions:**
| Shortcut | Chức năng |
|---|---|
| `Ctrl+S` | Save |
| `Shift+D` | Download selected screen(s) |
| `?` | Mở danh sách tất cả shortcuts |

### Command Palette — `Ctrl+K`

Universal search cho MỌI action trong Stitch:
- Hiển thị commands theo context hiện tại
- Gõ vài chữ → filter ngay
- Arrow keys để navigate, Enter để thực thi
- Quên shortcut nào? → `Ctrl+K` + gõ tìm

### Tap vs Hold — Chuyển tool tạm thời

Đây là feature rất hay mà nhiều người không biết:

| Hành vi | Kết quả |
|---|---|
| **Tap** `V`, `H`, `Z` | Chuyển tool **vĩnh viễn** |
| **Hold** `Space` | Pan **tạm thời** — thả ra về tool cũ |
| **Hold** `Z` | Zoom **tạm thời** — thả ra về tool cũ |

→ Bạn ở Select mode → giữ Space kéo canvas → thả Space → lại ở Select mode. Không cần click đổi tool.

### Screen Navigation

| Shortcut | Chức năng |
|---|---|
| `Ctrl+→` | Nhảy sang screen tiếp theo |
| `Ctrl+←` | Nhảy về screen trước |

Khi nhảy, Stitch tự động: select screen → zoom vừa → center lên giữa màn hình.

Thứ tự screen: **trái→phải, trên→dưới** (reading order).

Lạc trên canvas? → `Ctrl+←` snap về screen gần nhất, hoặc `0` zoom ra xem toàn bộ project.

### Workflow mẫu kết hợp tất cả

```
Ctrl+K   → Mở Command Palette → Generate screen mới
Ctrl+→   → Nhảy đến screen vừa tạo (auto zoom + select)
V        → Select mode → click screen
Space    → Giữ để pan, thả ra vẫn ở Select
Z        → Tap → kéo rectangle quanh component → zoom vào
Ctrl+D   → Duplicate screen
?        → Quên shortcut nào thì mở xem
```

**Advanced combos:**
- Select nhiều screens → `Shift+D` → download tất cả cùng lúc
- Giữ `Space` trong Zoom mode → pan tạm mà không đổi tool
- `Ctrl+A` → `Ctrl+D` → duplicate toàn bộ project layout

---

## 🧠 Tóm tắt Mental Model

> Nếu chỉ nhớ 5 điều từ tất cả 6 lessons:

**1. Iterate > Perfect Prompt**
Prompt đầu tiên chỉ cần Idea + Theme + Content. Sức mạnh nằm ở vòng lặp cải thiện.

**2. Một thay đổi lớn mỗi lần (Edit) — Swing lớn khi dùng Variations**
Đừng nhầm 2 context này. Edit = chính xác. Variations = khám phá.

**3. Translate, không Resize**
App ↔ Web khác nhau về navigation, layout, hierarchy — phải viết prompt giải thích cách tổ chức lại.

**4. Chọn đúng Design Mode cho đúng việc**
Logic phức tạp → 3 Pro. Đổi vibe → Redesign. HTML chất → 2.5 Pro. Nhanh → Fast.

**5. Prompt cụ thể = Kết quả tốt**
Dùng UI/UX keywords. Target element cụ thể. Mô tả hành động rõ ràng. Đừng nói "make it better".
