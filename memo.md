# Memo Teardown — Claude

**Nhóm báo cáo:** Đường Bốn mùa xuân  

**Thành viên:**  
- **Vũ Thế Lực** — 2A202602008  
- **Hoàng Tuấn Hưng** — 2A202601911  
- **Nguyễn Thị Nam Phương** — 2A202601720  
- **Đỗ Thị Thanh Loan** — 2A202601654  

**Sản phẩm:** Claude — Anthropic  
**Thời điểm phân tích:** 08/2026

## Vì sao chọn sản phẩm này?

Claude có một chuỗi quyết định sản phẩm đủ rõ để quan sát sự dịch chuyển từ **AI trả lời trong chat → AI tạo work product → AI kết nối tool/data → AI agent nhận và thực hiện công việc**. Nhóm chọn Claude vì chuỗi này vừa có nguồn công khai để kiểm chứng, vừa tạo được một câu chuyện Product Sense xuyên suốt từ timeline, user/JTBD đến dự đoán 6–12 tháng tới.

> **Product thesis của nhóm:** Anthropic đang liên tục tăng “đơn vị công việc” mà người dùng có thể giao cho Claude: từ một prompt, một tài liệu, một artifact, đến một tác vụ nhiều bước và cuối cùng là một workflow có thể ủy quyền cho agent.

---

# §1. Timeline các cập nhật lớn

| Thời điểm | Cập nhật | Context lúc đó | Nguyên lý / framework |
|---|---|---|---|
| **14/03/2023** | Claude và Claude Instant được giới thiệu rộng hơn sau giai đoạn closed alpha với các partner như Notion, Quora và DuckDuckGo. [Nguồn gốc](https://www.anthropic.com/news/introducing-claude) | Anthropic đi sau ChatGPT ở kênh consumer, nhưng đã có distribution qua các sản phẩm/đối tác và developer API. | **Moat / distribution wedge:** không nhất thiết đánh trực diện vào cùng kênh; dùng partner + API để đi vào use case thật và tích lũy learning trước khi mở rộng. |
| **11/05/2023** | Context window tăng từ **9K lên 100K tokens** (~75.000 từ). [Nguồn gốc](https://www.anthropic.com/news/100k-context-windows) | Context ngắn khiến user phải chunk tài liệu, chia nhỏ code hoặc tự dựng pipeline để xử lý đầu vào dài. | **x10:** thay đổi bậc độ lớn ở một trục user thực sự cảm nhận được. 100K không chỉ “tốt hơn 10%” mà mở ra job mới: đọc cả bộ tài liệu/codebase trong một lần. |
| **04/03/2024** | Ra mắt bộ Claude 3: **Haiku – Sonnet – Opus**, cho phép chọn trade-off giữa intelligence, speed và cost. [Nguồn gốc](https://www.anthropic.com/news/claude-3-family) | Thị trường bắt đầu phân hóa theo workload: có task cần rẻ/nhanh, có task cần reasoning sâu. | **Định nghĩa “tốt”:** không có một model tốt nhất cho mọi job; “tốt” phải được định nghĩa theo quality × latency × cost của từng use case. |
| **21/06/2024** | Claude 3.5 Sonnet + **Artifacts**, tạo cửa sổ riêng để xem, sửa và phát triển output ngay bên cạnh chat. [Nguồn gốc](https://www.anthropic.com/news/claude-3-5-sonnet) | Cuộc đua AI chuyển từ chỉ trả lời tốt sang tích hợp output vào workflow. Anthropic mô tả Artifacts là bước Claude tiến từ conversational AI sang collaborative work environment. | **Wrapper → moat:** capability của model chỉ thành sản phẩm khi được đóng gói vào interaction/workflow. Artifacts tạo “nơi chứa work product”, tăng giá trị vượt khỏi ô chat. |
| **25/11/2024** | Anthropic open-source **Model Context Protocol (MCP)** — chuẩn mở kết nối AI với data source, business tool và development environment. [Nguồn gốc](https://www.anthropic.com/news/model-context-protocol) | Mỗi nguồn dữ liệu/tool cần một integration riêng; agent bị cô lập khỏi dữ liệu thật. | **Moat qua ecosystem/open standard:** giảm integration friction để hệ sinh thái cùng xây connector. Đây không phải lock-in độc quyền; moat nằm ở adoption, ecosystem influence và khả năng Claude tham gia nhiều workflow hơn. |
| **22/05/2025** | Claude Opus 4 & Sonnet 4; **Claude Code GA**, hỗ trợ background tasks, IDE integrations và agent SDK. [Nguồn gốc](https://www.anthropic.com/news/claude-4) | Computer Use beta và Claude Code preview đã thử nghiệm “AI hành động”; Claude 4 nhấn mạnh coding, long-running tasks và agent workflows. | **Vertical AI + định nghĩa lại “tốt”:** với software engineering, “tốt” không còn là trả lời đúng một câu mà là hoàn thành được task nhiều bước, giữ context và tự kiểm tra kết quả. |
| **12/01/2026** | **Claude Cowork** ra research preview, mang agentic capabilities của Claude Code sang desktop và knowledge work ngoài coding. Đến 07/2026 Cowork mở rộng lên web/mobile và có thể chạy task từ xa. [Nguồn](https://www.anthropic.com/news/introducing-anthropic-labs) · [Cowork](https://claude.com/product/cowork) | Claude Code chứng minh mô hình “delegate work to agent” trong dev; bước tiếp theo là mở abstraction đó sang broader knowledge work. | **Định nghĩa lại “tốt” ở cấp outcome:** user không chỉ cần câu trả lời hoặc code snippet; họ giao mục tiêu, Claude tự tìm cách đi từ đầu đến cuối trong file/tool được cấp quyền. |

### Vì sao chọn những mốc này?

Bảy mốc trên không phải danh sách model release, mà là bảy lần **hình dạng của sản phẩm hoặc đơn vị giá trị thay đổi**: distribution qua partner → long context → model portfolio → workspace cho work product → open integration layer → vertical execution agent → general work agent.

Nhóm cân nhắc nhưng loại:
- **22/10/2024 – Computer Use (beta):** quan trọng về kỹ thuật nhưng cùng trục “AI từ trả lời → hành động” với Claude Code; nếu timeline chỉ 6–8 dòng, Claude Code GA thể hiện product commitment rõ hơn.
- **24/02/2025 – Claude 3.7 + Claude Code research preview:** là mốc bắt đầu quyết định coding agent, nhưng để tránh lặp, nhóm giữ mốc GA 22/05/2025.
- **09/04/2025 – Claude Max:** có giá trị cho phân tích monetization, nhưng không thay đổi core workflow mạnh bằng Artifacts/MCP/Claude Code/Cowork.

---

# §2. Tệp user & JTBD

> **Lưu ý cách đọc:** Claude hiện có nhiều segment. Nhóm chọn một segment đại diện có shift quan sát rõ nhất: **technical builder / founder dùng Claude để xử lý workflow phức tạp và ủy quyền công việc cho agent**.

| | Early adopters | Tệp hiện tại |
|---|---|---|
| **Đặc điểm** | Kỹ sư/AI builder ở startup đang đưa LLM vào production; nhạy với context limit, API cost và độ ổn định output. Một evidence đại diện là Marc Mengler (Octomind), người đánh giá Claude 2 cho use case viết, duy trì và “heal” E2E UI tests. [Review](https://www.producthunt.com/products/claude/reviews?filter=founder&founderReview=349570&page=1) | Technical founder / product builder đã quen dùng agent, muốn giao công việc chạy nền và điều phối nhiều agent thay vì tự prompt từng bước. Evidence đại diện: Abhishek Yadav mô tả dùng Claude từ mobile, để harness/self-review chạy như một “owner”, giúp anh tập trung xây sản phẩm và nói chuyện với user. [Review](https://www.producthunt.com/products/claude) |
| **JTBD chính** | **Khi** codebase/tài liệu/test suite quá lớn để xử lý liền mạch, **tôi muốn** đưa nhiều context vào model trong một lần và nhận output nhất quán, **để** giảm chunking, manual repair và chi phí vận hành pipeline. | **Khi** tôi đã xác định outcome của một product/software task, **tôi muốn** ủy quyền phần lớn chu trình triển khai cho Claude/agents chạy nền và chỉ review ở checkpoint quan trọng, **để** dành thời gian cho quyết định sản phẩm, khách hàng và công việc có leverage cao hơn. |
| **Trước đó họ làm bằng cách nào** | Cắt nhỏ file/tài liệu cho vừa context; dùng model context lớn với chi phí cao hơn; dựng RAG/pipeline thủ công; tự sửa code/hallucination sau mỗi vòng. | Copy/paste qua lại giữa design tool – chat – IDE – browser; tự chuyển output giữa các công cụ; ngồi trước máy để prompt và kiểm tra từng bước; tự điều phối các agent rời rạc. |

## Dịch chuyển tệp

Sự dịch chuyển không xảy ra bởi một mốc duy nhất mà theo chuỗi:

1. **100K context (05/2023)** mở JTBD “đưa cả khối công việc lớn vào cùng một context” — giảm nhu cầu chunking.
2. **Artifacts (06/2024)** biến Claude từ nơi trả lời thành nơi tạo/chỉnh một work product.
3. **Claude Code GA (05/2025)** nâng đơn vị giao việc từ “hãy giúp tôi code” thành “hãy thực hiện software task này”.
4. **Cowork (01/2026)** mở abstraction agent từ developer sang broader knowledge worker: user đưa goal, Claude làm qua file/tool, nhiều bước và có thể tiếp tục trong background.

=> **Segment shift cốt lõi:** từ người dùng thuê Claude để **xử lý thông tin tốt hơn** sang người dùng thuê Claude để **nhận trách nhiệm thực thi một phần công việc**.

## Switching cost — 4 Forces

| Force | Quan sát với Claude |
|---|---|
| **Push — lực đẩy khỏi cách cũ** | Context ngắn; phải chunk dữ liệu; chi phí API cao cho context lớn; copy/paste giữa nhiều tool; phải “babysit” AI từng bước; design → code → test bị đứt gãy. |
| **Pull — lực kéo sang Claude** | Long context; perceived quality về reasoning/coding; Artifacts tạo work product; Claude Code/Cowork cho phép self-review, tool use, background work và delegation nhiều bước. |
| **Anxiety — bất an khi switch** | Rate limit/chi phí; agent có thể thực thi sai trong workflow dài; quyền truy cập dữ liệu/tool; khó audit; khoảng cách giữa các surface như Design → Code nếu handoff chưa liền mạch. |
| **Habit — lực níu từ giải pháp cũ** | User đã quen IDE, ChatGPT, Google/Microsoft Workspace; dữ liệu và workflow nằm ở nền tảng khác; thói quen thao tác thủ công và quy trình approval hiện có. |

### Lực mạnh nhất và rủi ro nếu nó biến mất

Với segment technical builder mà nhóm chọn, lực mạnh nhất hiện nay là **Pull từ chất lượng output + khả năng delegation**. Nhưng đây cũng là rủi ro: nếu OpenAI/Google đạt chất lượng coding/reasoning/agent tương đương với giá và distribution tốt hơn, switching cost của nhóm power user có thể thấp.

Điều đó tạo một bài toán chiến lược cho Anthropic: **Claude phải biến lợi thế model thành workflow moat — qua context, MCP/connectors, skills, team context, agent runtime và vertical solutions — trước khi model advantage bị commoditize.**

---

# §3. Ba dự đoán hướng đi trong 6–12 tháng tới

> Các dự đoán dưới đây là **forecast của nhóm**, không phải roadmap Anthropic đã công bố. Nhóm dùng §1–§2 làm nền và kiểm tra thêm bằng các tín hiệu công khai đến 08/2026.

## Dự đoán 1 — Claude sẽ tiến từ “agent được gọi khi cần” thành proactive/team work agent

**Loại:** Mở rộng tính năng + đe dọa Big Tech

- **Dự đoán:** Claude sẽ tăng khả năng chạy công việc dài/định kỳ trong background, giữ context của team và chủ động tiếp tục workflow; human chuyển dần sang vai trò giao goal, đặt permission và approve checkpoint thay vì prompt từng bước.
- **Lập luận:** §1 cho thấy chuỗi **Artifacts → MCP → Claude Code → Cowork** liên tục tăng mức delegation; §2 current JTBD đã chuyển sang “giao cả workflow và review kết quả”. Tín hiệu hiện tại củng cố pattern: [Claude Tag](https://www.anthropic.com/news/introducing-claude-tag) cho Claude tham gia Slack như một team member, có context và plan task tương lai. Trong khi đó [OpenAI Workspace Agents](https://openai.com/index/introducing-workspace-agents-in-chatgpt/) và [Google Gemini Spark](https://blog.google/innovation-and-ai/products/gemini-app/next-evolution-gemini-app/) đều đẩy agent cloud/background, nên Anthropic khó dừng ở mô hình reactive.

**Giả định dễ gãy:** reliability/permission của long-running agent phải đủ cao để doanh nghiệp cho phép Claude tự hành động.

## Dự đoán 2 — Anthropic sẽ đóng gói thêm nhiều “Claude for X” / vertical agents

**Loại:** Mở rộng segment

- **Dự đoán:** Claude sẽ có thêm các gói/agent/skills chuyên theo role hoặc ngành, ưu tiên những workflow giá trị cao như finance, legal, science, security, healthcare và enterprise knowledge work.
- **Lập luận:** §1 cho thấy Anthropic đã quen dùng **wedge theo use case** (partner/API), sau đó tạo một vertical rõ ràng là **Claude Code**; MCP giúp nối dữ liệu/tool của từng domain. §2 cho thấy user trả tiền cho outcome cụ thể hơn là “chat hay”. Tín hiệu 2026 đã đi đúng hướng này với [Agents for Financial Services](https://www.anthropic.com/news/finance-agents), [Claude for Small Business](https://www.anthropic.com/news/claude-for-small-business), [Claude for Teachers](https://www.anthropic.com/news/claude-for-teachers) và [Claude Science](https://www.anthropic.com/news/claude-science-ai-workbench).

**Giả định dễ gãy:** vertical package phải tạo giá trị vượt đủ xa so với việc user tự dùng Claude chung + prompt/connector.

## Dự đoán 3 — Claude sẽ nối các work product thành workflow end-to-end, giảm handoff giữa Design → Implementation → Review

**Loại:** Mở rộng tính năng + mở rộng segment

- **Dự đoán:** Claude sẽ hợp nhất sâu hơn các surface tạo artifact, design, code, document/spreadsheet/slide và review vào một orchestration layer chung; user mô tả outcome và Claude tự chuyển giao công việc giữa các bước/agent thay vì user tự download–copy–paste.
- **Lập luận:** §1: Artifacts đã tạo “nơi chứa output”, Claude Code biến output thành execution và Cowork mở execution sang knowledge work. §2: current user evidence nêu thẳng pain point **Design → Code handoff** và mong muốn workflow **design → implementation → review**. Các tín hiệu mới như [Claude Design](https://www.anthropic.com/news/claude-design-anthropic-labs) và khả năng [tạo/chỉnh file trực tiếp](https://www.anthropic.com/news/create-files) làm cho bước tiếp theo hợp lý là nối các work product thành một chuỗi thực thi thay vì nhiều feature độc lập.

**Giả định dễ gãy:** Anthropic phải giải quyết được consistency/context giữa nhiều surface và tránh workflow quá “black box” khiến user mất khả năng kiểm soát.

---

# §4. AI Log

| Việc | AI làm hay nhóm làm? | Nhóm kiểm chứng/phán đoán lại thế nào? |
|---|---|---|
| Tìm và tổng hợp candidate milestones của Claude | **Nhóm research, AI hỗ trợ tổng hợp** | Mở lại link gốc của Anthropic; chỉ giữ mốc thay đổi product/workflow, loại bugfix/model update trùng nguyên lý. |
| Revert từng milestone về nguyên lý | **AI hỗ trợ đề xuất wording; nhóm quyết định** | Đối chiếu với framework đã học (x10, wrapper/moat, Vertical AI, định nghĩa “tốt”); bỏ các nhãn generic không giải thích được “vì sao”. |
| Xác định Early adopter / Current user và JTBD | **Nam Phương research; AI hỗ trợ cấu trúc** | Đối chiếu review gốc Product Hunt; tách feature khỏi “job cần làm”; không coi một persona là toàn bộ user base của Claude. |
| Tổng hợp tín hiệu 2026 và brainstorm Forecast | **Lực + ChatGPT hỗ trợ research/synthesis** | Ưu tiên nguồn chính thức Anthropic/OpenAI/Google; phân biệt rõ “tín hiệu đã xảy ra” và “dự đoán của nhóm”. |
| Chọn 3 prediction cuối | **Cả nhóm** | Mỗi prediction phải truy ngược được về ít nhất một milestone §1 và một insight user/JTBD §2; loại dự đoán chung chung kiểu “sẽ thêm nhiều AI feature”. |
| Ghép và viết `memo.md` | **ChatGPT hỗ trợ soạn bản hợp nhất** | Cả nhóm đọc lại, kiểm tra ngày/link/claim, chỉnh nguyên lý và chịu trách nhiệm với reasoning cuối trước khi nộp. |

---

# Kết luận

Chuỗi quyết định của Claude có thể được tóm tắt bằng một sự thay đổi abstraction:

**Đọc nhiều hơn → tạo work product → kết nối dữ liệu/tool → thực thi task → nhận responsibility cho workflow.**

Điểm đáng chú ý không phải Anthropic ra nhiều model hơn, mà là **mỗi lớp capability mới được đóng gói thành một mức delegation cao hơn**. Vì vậy, ba hướng nhóm dự đoán — proactive team agent, vertical agents và workflow end-to-end — đều xuất phát từ cùng một pattern lịch sử và cùng một JTBD mới: **người dùng muốn giao outcome cho AI thay vì tự điều khiển từng thao tác.**

---

# Nguồn chính

## Timeline / Anthropic
1. [Introducing Claude — 14/03/2023](https://www.anthropic.com/news/introducing-claude)
2. [Introducing 100K Context Windows — 11/05/2023](https://www.anthropic.com/news/100k-context-windows)
3. [Introducing the next generation of Claude / Claude 3 — 04/03/2024](https://www.anthropic.com/news/claude-3-family)
4. [Claude 3.5 Sonnet + Artifacts — 21/06/2024](https://www.anthropic.com/news/claude-3-5-sonnet)
5. [Model Context Protocol — 25/11/2024](https://www.anthropic.com/news/model-context-protocol)
6. [Claude 4 + Claude Code GA — 22/05/2025](https://www.anthropic.com/news/claude-4)
7. [Introducing Anthropic Labs / Cowork — 13/01/2026](https://www.anthropic.com/news/introducing-anthropic-labs)
8. [Claude Cowork](https://claude.com/product/cowork)

## User evidence
9. [Product Hunt — Marc Mengler / Claude review](https://www.producthunt.com/products/claude/reviews?filter=founder&founderReview=349570&page=1)
10. [Product Hunt — Claude reviews / Abhishek Yadav](https://www.producthunt.com/products/claude)

## Signals for Forecast
11. [Claude Tag — 23/06/2026](https://www.anthropic.com/news/introducing-claude-tag)
12. [Agents for Financial Services — 05/05/2026](https://www.anthropic.com/news/finance-agents)
13. [Claude for Small Business — 13/05/2026](https://www.anthropic.com/news/claude-for-small-business)
14. [Claude for Teachers — 14/07/2026](https://www.anthropic.com/news/claude-for-teachers)
15. [Claude Science — 30/06/2026](https://www.anthropic.com/news/claude-science-ai-workbench)
16. [Claude Design — 17/04/2026](https://www.anthropic.com/news/claude-design-anthropic-labs)
17. [Claude can create and edit files](https://www.anthropic.com/news/create-files)
18. [OpenAI Workspace Agents — 22/04/2026](https://openai.com/index/introducing-workspace-agents-in-chatgpt/)
19. [Google Gemini Spark — 19/05/2026](https://blog.google/innovation-and-ai/products/gemini-app/next-evolution-gemini-app/)
