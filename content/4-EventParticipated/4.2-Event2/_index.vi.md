---
title: "Event 2"
date: 2026-05-23
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

# BÀI THU HOẠCH "FCAJ COMMUNITY DAY - AI, CLOUD VÀ ENTERPRISE SYSTEMS"

### Mục Đích Của Sự Kiện

Sự kiện **FCAJ Community Day** là một buổi chia sẻ cộng đồng dành cho các bạn đang học và làm việc trong lĩnh vực AWS, Cloud, AI, DevOps, Software Engineering và phát triển sản phẩm công nghệ.

Điểm nổi bật của sự kiện là các phần chia sẻ không chỉ tập trung vào lý thuyết kỹ thuật, mà còn gắn với kinh nghiệm thực tế từ doanh nghiệp, dự án thật, hackathon, vận hành hệ thống production và tư duy nghề nghiệp trong thời đại AI.

Các mục tiêu chính của sự kiện gồm:

- Giúp người tham gia hiểu rõ hơn về xu hướng việc làm trong thời đại AI.
- Chia sẻ cách chuẩn bị kiến thức, sản phẩm và tư duy để cạnh tranh trên thị trường lao động.
- Giới thiệu cách sử dụng AI hiệu quả thông qua context, prompt, AI mindset và AI adoption.
- Trình bày các ứng dụng AI thực tế như Amazon Q, agent, dashboard, meeting summarization và workflow automation.
- Chia sẻ kiến thức chuyên sâu về Amazon CloudFront, CDN, pricing, security, cost optimization và high availability.
- Trình bày kinh nghiệm tham gia hackathon và cách xây dựng sản phẩm trong thời gian ngắn.
- Giải thích cách tối ưu độ ổn định của output khi làm việc với Large Language Models.
- Giới thiệu tư duy xây dựng enterprise-grade multi-agent system cho bài toán nghiệp vụ thực tế.
- Nhấn mạnh vai trò của security, compliance, audit trail, guardrails và mindset sản phẩm trong doanh nghiệp.

### Danh Sách Diễn Giả / Người Chia Sẻ

Dựa trên transcript, sự kiện gồm nhiều phần chia sẻ từ các diễn giả khác nhau:

- **Quỳnh Mai**: Người dẫn chương trình, giới thiệu tinh thần kết nối và chia sẻ của FCAJ Community Day.
- **Anh Nguyễn Gia Hưng**: AWS Solution Architect tại AWS Việt Nam và người sáng lập FCAJ, chia sẻ về thị trường việc làm, AI và cách sinh viên cần chuẩn bị cho tương lai.
- **Anh Tịnh Trương**: Platform Engineer tại Gotam X, chia sẻ về context, prompt, AI mindset, AI adoption và cách sử dụng AI hiệu quả hơn.
- **Hải Anh**: Chia sẻ về Amazon Q, agent, business intelligence, dashboard, automation và meeting summarization.
- **Nguyễn Hấn Thịnh**: DevOps Engineer, chia sẻ chuyên sâu về Amazon CloudFront, flat-rate pricing, bảo mật, tối ưu chi phí và hiệu năng.
- **Nhóm UTM Morpho**: Chia sẻ hành trình tham gia hackathon 36 giờ, quá trình hình thành ý tưởng, xây dựng sản phẩm và bài học rút ra.
- **Diễn giả về LLM Determinism**: Chia sẻ về temperature, token generation, inference optimization và vì sao output của LLM vẫn có thể thay đổi dù temperature bằng 0.
- **Diễn giả cuối về Enterprise Multi-Agent System**: Chia sẻ về cách thiết kế multi-agent system cho bài toán đánh giá tín dụng startup trong môi trường doanh nghiệp.

---

## 1. Phần Mở Đầu - Thị Trường Việc Làm Và Tác Động Của AI

### Nội Dung Chính

Phần mở đầu được chia sẻ bởi **anh Nguyễn Gia Hưng**, AWS Solution Architect tại AWS Việt Nam và là người sáng lập FCAJ.

Anh bắt đầu bằng việc đặt câu hỏi về tình hình thị trường việc làm hiện tại. Nhiều bạn trẻ cảm thấy thị trường IT đang khó hơn, đặc biệt là khi AI ngày càng mạnh. Tuy nhiên, anh Hưng đưa ra một góc nhìn khác: khi một công nghệ làm cho việc tạo phần mềm trở nên rẻ hơn, nhu cầu tạo phần mềm sẽ không giảm mà còn tăng mạnh.

Anh sử dụng ví dụ về **bóng đèn LED**. Khi bóng đèn LED giúp chi phí chiếu sáng rẻ hơn rất nhiều, con người không dùng ít ánh sáng hơn. Ngược lại, nhu cầu chiếu sáng tăng lên, từ nhà cửa, cầu thang, vườn cây cho đến thành phố ban đêm. Tương tự, khi AI giúp việc phát triển phần mềm rẻ hơn và nhanh hơn, số lượng phần mềm được tạo ra trong tương lai sẽ tăng rất nhiều.

### AI Không Làm Mất Hết Việc, Nhưng Làm Thay Đổi Loại Công Việc

Một ý quan trọng trong phần chia sẻ là AI có thể khiến việc tạo phần mềm dễ hơn, nhưng điều đó cũng tạo ra nhiều công việc mới.

Trước đây, nhiều người có ý tưởng nhưng không đủ tiền thuê đội ngũ kỹ thuật để xây dựng sản phẩm. Hiện nay, nhờ AI, cả những người không thuộc ngành IT như luật sư, bác sĩ hoặc người làm kinh doanh cũng có thể tạo ra MVP hoặc prototype.

Tuy nhiên, khi sản phẩm được tạo ra nhiều hơn, sẽ phát sinh nhu cầu mới:

- Sửa lỗi cho các sản phẩm được tạo bằng AI.
- Maintain các MVP chưa đủ chuẩn production.
- Scale hệ thống khi có người dùng thật.
- Vận hành, bảo mật và tối ưu hệ thống.
- Xây dựng platform và infrastructure để sản phẩm chạy ổn định.
- Chuyển demo thành sản phẩm dùng được trong doanh nghiệp.

Vì vậy, thay vì chỉ lo lắng AI thay thế lập trình viên, người học cần hiểu rằng AI đang làm thay đổi yêu cầu của thị trường.

### Vì Sao Giai Đoạn Hiện Tại Khó Khăn?

Anh Hưng giải thích rằng hiện tại là một giai đoạn chuyển giao. Các công ty lớn đang đầu tư mạnh vào hạ tầng AI, phần cứng AI và mô hình AI. Trong quá trình đó, họ cũng phải tối ưu chi phí, dẫn đến ảnh hưởng ngắn hạn đến việc làm.

Tuy nhiên, trong dài hạn, nhu cầu phần mềm và các công việc liên quan đến phần mềm vẫn có xu hướng tăng.

Đối với Việt Nam, anh nhắc lại rằng ngành công nghệ thông tin Việt Nam lâu nay có thế mạnh lớn về **outsourcing**. Nhiều tổ chức quốc tế mở technical hub tại Việt Nam vì có nguồn nhân lực tốt. Do đó, sinh viên không nên chỉ nhìn vào thị trường nội địa, mà cần chuẩn bị để cạnh tranh với thị trường toàn cầu.

### Những Điều Sinh Viên Cần Chuẩn Bị

Anh Hưng nhấn mạnh rằng chỉ có bằng đại học hoặc kiến thức kỹ thuật cơ bản là chưa đủ.

Người học cần chuẩn bị thêm:

- Nền tảng kỹ thuật vững.
- Kiến thức thực tế về ngành muốn làm việc.
- Hiểu use case thật của doanh nghiệp.
- Có sản phẩm thật thay vì chỉ có demo.
- Kỹ năng mềm, tiếng Anh, networking và personal branding.
- Khả năng trình bày giá trị mình có thể đóng góp cho tổ chức.

Ví dụ, nếu muốn làm AI Engineer trong ngân hàng, người học không nên chỉ mang các bài tập như nhận diện biển số xe hoặc nhận diện kệ hàng để trình bày. Thay vào đó, cần hiểu ngân hàng có những bài toán gì, hệ thống nào, use case nào và AI có thể tạo giá trị ra sao.

### Sản Phẩm Quan Trọng Hơn Demo

Một thông điệp rất rõ trong phần mở đầu là:

```text
Thị trường hiện nay cần sản phẩm, không chỉ cần demo.
```

Trước đây, sinh viên có thể chỉ cần làm project hoặc demo nhỏ. Nhưng trong thời đại AI, khi người không chuyên IT cũng có thể tạo ra sản phẩm, kỹ sư phần mềm cần chứng minh rằng mình có khả năng tạo ra thứ có thể vận hành, maintain và scale.

Một sản phẩm tốt nên thể hiện được:

- Có người dùng hoặc use case rõ ràng.
- Có kiến trúc hợp lý.
- Có khả năng deploy.
- Có khả năng vận hành.
- Có monitoring.
- Có security.
- Có tài liệu.
- Có khả năng mở rộng.

### Bài Học Rút Ra

- AI không chỉ làm giảm việc làm, mà còn tạo ra nhu cầu phần mềm và các loại công việc mới.
- Người học cần chuẩn bị nhiều hơn ngoài kiến thức kỹ thuật.
- Sản phẩm thực tế sẽ có giá trị hơn demo đơn giản.
- Kiến thức doanh nghiệp và use case ngành là lợi thế lớn khi đi làm.
- Không nên trì hoãn việc học và làm project vì thị trường thay đổi rất nhanh.

---

## 2. Session 1 - Context, Prompt Và AI Mindset

### Giới Thiệu Chủ Đề

Phần chia sẻ tiếp theo do **anh Tịnh Trương**, Platform Engineer tại Gotam X, trình bày.

Chủ đề chính xoay quanh việc sử dụng AI hiệu quả hơn, đặc biệt là cách cung cấp **context** đúng cho AI. Anh không đi quá sâu vào một công nghệ cụ thể vì người tham gia có nhiều background khác nhau như developer, backend, frontend, UI/UX, DevOps hoặc sinh viên mới học.

Thay vào đó, anh chọn một chủ đề mở để mọi người có thể tự áp dụng vào background của mình.

### Platform Engineer Là Gì?

Anh giải thích ngắn gọn về vai trò **Platform Engineer**.

Trước đây, developer muốn deploy một application thường phải nhờ DevOps provision database, server, infrastructure hoặc resource. Nếu công ty có hàng trăm developer, việc mỗi request đều phải nhờ DevOps làm thủ công sẽ rất tốn thời gian.

Platform Engineer sẽ xây dựng nền tảng nội bộ để developer có thể tự tạo resource theo nhu cầu, nhưng vẫn nằm trong phạm vi kiểm soát của team platform. Nói cách khác, Platform Engineering giúp biến infrastructure thành một nền tảng tự phục vụ, có chuẩn hóa và quản trị.

### Vấn Đề Khi Dùng AI Không Có Context

Anh chỉ ra một lỗi phổ biến khi dùng ChatGPT hoặc AI tool: nhiều người dùng một đoạn chat duy nhất cho quá nhiều mục đích khác nhau.

Ví dụ trong cùng một chat:

- Hỏi lịch du lịch Hội An.
- Hỏi cách review CV.
- Hỏi kiến thức tuyển dụng.
- Hỏi code.
- Hỏi kiến thức AWS.
- Hỏi về công việc.

Khi context thay đổi liên tục, AI sẽ dễ bị rối vì không biết chính xác người dùng đang làm gì. Điều này giống như một người bị hỏi quá nhiều chủ đề khác nhau trong cùng một cuộc trò chuyện.

Vì vậy, khi làm việc với AI, cần cung cấp đúng ngữ cảnh cho từng công việc.

### Context Là Gì?

Context có thể hiểu là **ngữ cảnh**. AI có rất nhiều kiến thức tổng quát, nhưng để trả lời đúng với môi trường cụ thể của người dùng, người dùng cần cung cấp thông tin phù hợp.

Một context tốt nên bao gồm:

- Mục tiêu của người dùng.
- Vai trò của AI.
- Người dùng là ai.
- Dự án đang làm là gì.
- Môi trường công ty hoặc team có quy định riêng gì.
- Style code hoặc convention riêng.
- Tài liệu liên quan.
- Output mong muốn.

Ví dụ, nếu người dùng là người mới học AWS, nên nói rõ:

```text
Tôi là người mới học AWS. Hãy giải thích khái niệm này theo cách dễ hiểu, có ví dụ đơn giản.
```

Khi đó, AI sẽ giải thích chi tiết và dễ hiểu hơn so với việc chỉ yêu cầu "giải thích".

### Không Nên Đưa Quá Nhiều Thông Tin Không Cần Thiết

Một điểm quan trọng là context không có nghĩa là đưa càng nhiều càng tốt.

Nếu người dùng đưa quá nhiều thông tin mà AI đã biết sẵn, hoặc đưa nhiều tài liệu không liên quan, AI có thể bị loãng context. Điều này làm phản hồi kém chính xác hơn.

Anh gọi hiện tượng này là kiểu "Internet Puller", tức là thấy cái gì trên mạng hay cũng kéo về, plugin nào hay cũng thêm vào, rule nào hay cũng copy vào. Nhưng nếu không đọc lại và lọc lại, những rule đó có thể không phù hợp với project hoặc công ty của mình.

Ví dụ:

- Copy quá nhiều rule review code từ mạng.
- Thêm quá nhiều plugin AI.
- Dùng nhiều prompt framework nhưng không hiểu.
- Đưa quá nhiều tài liệu không liên quan vào context.
- Kết quả là AI follow sai rule hoặc trả lời không đúng nhu cầu.

Do đó, cần chọn lọc context:

```text
Context đúng > Context nhiều
```

### AI First Mindset Và AI Adoption

Anh gợi ý hai keyword quan trọng để người học tự tìm hiểu thêm:

- **AI First Mindset**
- **AI Adoption**

AI First Mindset có thể hiểu là tư duy xem AI như một công cụ hỗ trợ thường xuyên trong công việc, nhưng không dùng AI một cách mù quáng. Người dùng cần biết khi nào nên dùng AI, dùng để làm gì và đánh giá kết quả như thế nào.

AI Adoption là quá trình doanh nghiệp áp dụng AI vào quy trình làm việc, sản phẩm và vận hành. Người học cần hiểu xu hướng này vì các công ty lớn đang bắt đầu đánh giá ứng viên dựa trên khả năng biết sử dụng AI đúng cách.

### Second Brain Và AI Context

Anh cũng nhắc đến khái niệm **Second Brain**.

Second Brain là cách tổ chức lại ghi chú, tài liệu, kiến thức và trải nghiệm cá nhân thành một hệ thống có thể truy xuất lại. Khi kết hợp với AI, người dùng có thể dùng second brain để cung cấp context chất lượng hơn cho AI.

Ví dụ, thay vì mỗi lần hỏi AI lại phải giải thích lại toàn bộ dự án, người dùng có thể có sẵn:

- Tài liệu dự án.
- Quy tắc code.
- Kiến trúc hệ thống.
- Convention của team.
- Các quyết định kỹ thuật trước đó.
- Note học tập.

Khi đó, AI có thể hiểu người dùng tốt hơn và hỗ trợ chính xác hơn.

### Tự Tin Chia Sẻ Và Đặt Câu Hỏi

Một nội dung khác trong session là sự tự tin. Anh nhắc rằng trong phỏng vấn, có nhiều bạn có kiến thức nhưng không dám nói, không dám trả lời tiếng Anh hoặc không dám chia sẻ suy nghĩ.

Điều này làm giảm cơ hội trúng tuyển, đặc biệt trong bối cảnh thị trường fresher và intern cạnh tranh rất cao.

Vì vậy, người học cần:

- Tự tin đứng lên chia sẻ.
- Dám nói dù chưa hoàn hảo.
- Dám hỏi khi không biết.
- Dám trình bày suy nghĩ của mình.
- Luyện tập giao tiếp và thuyết trình.

### Bài Học Rút Ra

- AI cần context đúng để trả lời chính xác.
- Không nên dùng một chat cho quá nhiều chủ đề khác nhau.
- Không nên kéo quá nhiều rule, plugin hoặc prompt từ Internet mà không hiểu.
- Context nên tập trung vào những thứ riêng của project, team hoặc công ty.
- AI First Mindset và AI Adoption là các xu hướng cần tìm hiểu.
- Second Brain có thể giúp quản lý kiến thức và cung cấp context tốt hơn cho AI.
- Người học cần rèn luyện sự tự tin khi chia sẻ, hỏi đáp và phỏng vấn.

---

## 3. Session 2 - Amazon Q, Agent Và Workflow Automation

### Giới Thiệu Chủ Đề

Phần tiếp theo do **Hải Anh** trình bày. Diễn giả chia sẻ về Amazon Q và cách AI agent có thể hỗ trợ người dùng trong các công việc văn phòng, phân tích dữ liệu và tự động hóa quy trình.

Diễn giả mở đầu bằng việc chia sẻ về trải nghiệm cá nhân khi từng thuyết trình ở các sự kiện quốc tế như Singapore và Silicon Valley. Thông điệp chính là người trẻ hoàn toàn có thể tạo ra cơ hội nếu có sự tự tin, sản phẩm và khả năng giải quyết vấn đề thật cho người dùng.

### Vấn Đề Thực Tế

Trong doanh nghiệp, nhiều người như manager, senior, director hoặc CEO phải tốn rất nhiều thời gian để tổng hợp dữ liệu, làm báo cáo hàng tuần, đọc file Excel, phân tích số liệu, tóm tắt meeting hoặc gửi next step cho các bên liên quan.

Những công việc này thường:

- Lặp lại nhiều lần.
- Tốn thời gian.
- Không phải lúc nào cũng cần chuyên môn kỹ thuật sâu.
- Làm chậm quá trình ra quyết định.
- Làm người quản lý mất thời gian cho các việc quan trọng hơn.

Amazon Q được giới thiệu như một trợ lý AI thân thiện với người dùng, có thể giúp kết nối các nguồn dữ liệu và tự động hóa một phần công việc này.

### Agent Là Gì?

Diễn giả giải thích agent theo cách đơn giản.

Một Large Language Model thông thường giống như một bộ não có khả năng suy luận và trả lời. Nhưng nếu chỉ có bộ não, nó không thể tự hành động như đặt lịch, gửi email, lấy dữ liệu hoặc cập nhật hệ thống.

Agent là sự kết hợp giữa:

- Bộ não LLM.
- Các công cụ hoặc action.
- Khả năng kết nối tới dịch vụ bên ngoài.
- Workflow để thực hiện hành động.

Có thể hiểu agent giống như một LLM có thêm "cánh tay nối dài" để làm việc với Gmail, Calendar, Microsoft Teams, Confluence, Jira, Microsoft Cloud hoặc các hệ thống khác.

### Amazon Q Và Platform Agent

Amazon Q được trình bày như một nền tảng giúp người dùng tạo agent theo nhu cầu riêng.

Một số khả năng được nhắc đến:

- Kết nối với hệ sinh thái Microsoft như PowerPoint, Word, Teams.
- Kết nối với hệ sinh thái Google như Gmail, Calendar.
- Tạo dashboard phân tích dữ liệu.
- Chat trực tiếp với dữ liệu.
- Tự động hóa workflow.
- Tạo agent tóm tắt meeting.
- Gửi next step cho người liên quan thông qua email.
- Hỗ trợ user không có kỹ năng BI vẫn có thể phân tích dữ liệu.

### Demo Dashboard Từ File Excel

Trong phần demo, diễn giả mô tả một tình huống người dùng upload một file Excel chứa dữ liệu như sale order, doanh thu hoặc performance quý.

Trước đây, một người làm BI cần dùng công cụ như Microsoft BI hoặc OpenSearch để lập dashboard. Nhưng với Amazon Q, user có thể upload file Excel và yêu cầu AI tạo dashboard hoặc phân tích dữ liệu.

Ví dụ:

```text
Hãy phân tích dữ liệu sale order này và tạo dashboard tổng quan.
```

Sau đó, hệ thống có thể tạo ra phân tích trực quan và cho phép người dùng hỏi thêm bằng ngôn ngữ tự nhiên.

### Demo Meeting Summarization

Diễn giả cũng demo một flow khác: tạo agent để tóm tắt nội dung cuộc họp.

Agent có thể được cấu hình với vai trò:

```text
Meeting summarization assistant
```

Nhiệm vụ của agent là:

- Nhận transcript hoặc dữ liệu meeting.
- Tóm tắt overview.
- Liệt kê decision.
- Liệt kê action items.
- Xác định next steps.
- Gửi email hoặc tích hợp với Microsoft Teams nếu có kết nối.

Trong demo, do máy không kết nối email hoặc Microsoft Teams, diễn giả tập trung vào phần tóm tắt nội dung meeting.

### Tích Hợp Với MCP

Diễn giả cũng nhắc đến MCP như một cách mở rộng khả năng của LLM hoặc agent.

MCP có thể được hiểu như phần giúp agent kết nối với các công cụ, hệ thống hoặc hành động bên ngoài. Nhờ đó, agent không chỉ trả lời bằng text mà còn có thể gọi tool, xử lý dữ liệu và thực hiện workflow.

### Bài Học Rút Ra

- AI agent không chỉ trả lời câu hỏi mà còn có thể thực hiện hành động.
- Amazon Q có thể hỗ trợ phân tích dữ liệu, tạo dashboard và tự động hóa workflow.
- Người dùng không chuyên BI vẫn có thể tương tác với dữ liệu bằng ngôn ngữ tự nhiên.
- Meeting summarization và action item extraction là use case thực tế trong doanh nghiệp.
- Agent cần được kết nối với các hệ thống như email, calendar, Teams hoặc MCP để tạo giá trị thực tế.
- Khi xây dựng agent, cần quan tâm đến security, permission và dữ liệu doanh nghiệp.

---

## 4. Session 3 - Amazon CloudFront: Pricing, Security, Cost Optimization Và Performance

### Giới Thiệu Chủ Đề

Phần tiếp theo do **Nguyễn Hấn Thịnh**, DevOps Engineer, trình bày về **Amazon CloudFront**.

Amazon CloudFront thường được biết đến như một dịch vụ CDN của AWS, nhưng diễn giả nhấn mạnh rằng CloudFront không chỉ là CDN. Nó còn là nền tảng giúp tối ưu hiệu năng, bảo vệ ứng dụng và kiểm soát chi phí.

### Vấn Đề Với Pay-As-You-Go

Trước đây, khi dùng CloudFront theo mô hình pay-as-you-go, người dùng trả tiền theo mức sử dụng thực tế. Cách này có lợi khi traffic thấp vì chi phí có thể rất nhỏ. Tuy nhiên, nó cũng gây khó khăn trong việc dự đoán chi phí.

Một vấn đề lớn là khi traffic tăng bất thường, ví dụ:

- Website bị DDoS.
- Website bỗng viral.
- Bot gửi request nhiều.
- Lượng data transfer out tăng mạnh.

Khi đó, chi phí CDN có thể tăng đột biến và gây rủi ro lớn cho cá nhân, startup hoặc doanh nghiệp nhỏ.

### CloudFront Flat-Rate Pricing

Diễn giả giới thiệu cơ chế **flat-rate pricing** mới của CloudFront.

Thay vì chỉ dùng pay-as-you-go, AWS cung cấp các gói cố định như:

- Free.
- Pro.
- Business.
- Premium.

Người dùng chọn gói phù hợp với nhu cầu. Nếu vượt usage của gói, hệ thống có thể bị giới hạn băng thông hoặc chậm hơn, nhưng không phát sinh chi phí bất ngờ như mô hình pay-as-you-go.

Điều này giúp giải quyết nỗi lo lớn nhất của doanh nghiệp:

```text
Không dự đoán được bill cuối tháng.
```

### Nhóm Người Dùng CloudFront

AWS chia người dùng thành nhiều nhóm:

#### Small Website Owners

Nhóm này gồm cá nhân, website nhỏ, blog, startup nhỏ hoặc project học tập. Họ cần tăng performance và bảo vệ cơ bản với chi phí thấp.

#### Business Users

Nhóm này cần mức bảo vệ cao hơn, kiểm soát tốt hơn, private origin và tính năng bảo mật tốt hơn cho môi trường doanh nghiệp.

#### Mid-size / Large Enterprises

Nhóm này cần latency thấp, usage cao, origin failover, log reduction, high availability và bảo mật nâng cao.

### Hạ Tầng Mạng Của CloudFront

CloudFront hoạt động dựa trên mạng lưới edge locations và points of presence toàn cầu của AWS. Các điểm hiện diện này được kết nối với ISP gần người dùng để request đi đến hệ thống nhanh hơn.

AWS cũng có hệ thống backbone riêng, giúp dữ liệu di chuyển giữa các region và origin với tốc độ cao và ổn định hơn.

Trong trường hợp sự cố mạng như đứt cáp hoặc route bị lỗi, mạng của AWS có thể chuyển hướng traffic để người dùng vẫn truy cập được mà không nhận ra sự cố phía sau.

### Chống DDoS Và Volumetric Attack

CloudFront giúp chống các cuộc tấn công phân tán bằng cách chặn traffic gần nguồn tấn công hơn.

Nếu bot ở một quốc gia nào đó gửi traffic tới website, request sẽ đi qua edge location gần đó và có thể bị chặn tại edge, thay vì đi thẳng đến origin server.

Điều này giúp bảo vệ origin khỏi bị quá tải.

CloudFront cũng hỗ trợ các cơ chế như:

- Distributed defense.
- SYN proxy để chống SYN flood.
- Dashboard quan sát attack.
- Kết nối với đội ngũ hỗ trợ bảo mật 24/7 đối với các gói cao.

### Tối Ưu Chi Phí Với CloudFront

Diễn giả đưa ra ví dụ một website WordPress host trên EC2 có khoảng 150 GB data transfer out mỗi ngày.

Nếu không dùng CloudFront, origin như EC2 hoặc ALB phải xử lý nhiều request hơn, dẫn đến tăng chi phí data transfer, LCU usage và tải hệ thống.

Khi dùng CloudFront:

- CloudFront cache nội dung.
- Giảm request về origin.
- Giảm tải cho ALB.
- Giảm data transfer trực tiếp từ origin.
- Giảm CPU usage trên EC2.
- Giảm chi phí vận hành tổng thể.

### Content Compression

CloudFront có tính năng **content compression** giúp nén nội dung trước khi gửi về người dùng.

Khi bật tính năng này trong distribution behavior, CloudFront có thể giảm kích thước dữ liệu truyền đi. Điều này giúp:

- Website load nhanh hơn.
- Giảm data transfer.
- Giảm chi phí.
- Cải thiện trải nghiệm người dùng.

### Bảo Mật Với CloudFront

CloudFront hỗ trợ HTTPS thông qua tích hợp với AWS Certificate Manager. Người dùng có thể tạo TLS certificate và cấu hình HTTPS cho website dễ dàng.

AWS cũng sử dụng thư viện bảo mật riêng như **s2n** để tối ưu TLS handshake và giảm latency.

Ngoài ra, CloudFront còn hỗ trợ **mutual TLS (mTLS)**. Với mTLS, cả client và server đều cần certificate để xác thực lẫn nhau. Tính năng này phù hợp với các hệ thống cần bảo mật cao như tài chính, game độc quyền hoặc API nội bộ.

### Bảo Vệ Origin

CloudFront giúp ẩn origin và hạn chế việc người dùng truy cập trực tiếp vào server gốc.

Một số cách bảo vệ origin gồm:

- Dùng VPC Origin để kết nối CloudFront với origin trong private subnet.
- Dùng S3 Block Public Access.
- Chỉ cho phép CloudFront truy cập S3 hoặc origin.
- Giới hạn security group theo dải IP CloudFront.
- Thêm custom header để xác thực request từ CloudFront.
- Dùng geo restriction để chặn hoặc cho phép traffic theo quốc gia.
- Dùng signed URL hoặc signed cookies để bảo vệ nội dung riêng tư.

### Tăng Độ Tin Cậy Và Hiệu Năng

CloudFront hỗ trợ **origin failover**. Nếu origin chính gặp sự cố, CloudFront có thể chuyển request sang origin dự phòng để giữ website luôn hoạt động.

CloudFront cũng hỗ trợ custom error page để cải thiện trải nghiệm người dùng khi có lỗi.

Về hiệu năng, CloudFront có caching đa tầng:

```text
Viewer
  ↓
Point of Presence
  ↓
Regional Edge Cache
  ↓
Origin
```

Nếu có 10.000 request, CloudFront có thể gom lại và chỉ gửi một số lượng nhỏ request về origin, giúp server gốc tránh quá tải.

### HTTP/3 Và TCP Optimization

CloudFront hỗ trợ HTTP/3 với multiplexing, giúp xử lý nhiều request đồng thời và giảm thời gian tải trang.

Ngoài ra, CloudFront có thể tái sử dụng kết nối TCP tại edge location, giảm số lần handshake và tăng tốc độ phản hồi.

### CloudFront Functions

CloudFront Functions cho phép chạy logic nhẹ tại edge location.

Một số use case gồm:

- Redirect người dùng theo quốc gia.
- Rewrite URL.
- Chuyển hướng theo thiết bị mobile hoặc desktop.
- Xử lý header.
- Tối ưu routing trước khi request về origin.

### Bài Học Rút Ra

- CloudFront không chỉ là CDN, mà còn hỗ trợ security, performance và cost optimization.
- Flat-rate pricing giúp giảm rủi ro bill tăng đột biến.
- CloudFront giúp giảm tải cho origin và giảm chi phí data transfer.
- Content compression, caching, HTTP/3 và edge functions giúp cải thiện performance.
- VPC Origin, signed URL, geo restriction và mTLS giúp tăng bảo mật.
- Origin failover và custom error page giúp tăng độ tin cậy của hệ thống.

---

## 5. Session 4 - Hành Trình 36 Giờ Hackathon Với Dự Án UTM Morpho

### Giới Thiệu Chủ Đề

Phần tiếp theo là chia sẻ từ nhóm **UTM Morpho** về hành trình tham gia một cuộc thi hackathon kéo dài 36 giờ.

Tên dự án **UTM** được lấy từ chữ cái đầu của ba thành viên trong nhóm, còn **Morpho** mang ý nghĩa mới mẻ, thể hiện tinh thần tạo ra điều mới và hữu ích trong quá trình làm việc.

### Lý Do Tham Gia Hackathon

Nhóm biết đến cuộc thi thông qua đồng nghiệp. Cuộc thi có format là trong 36 giờ liên tục, các đội phải xây dựng một sản phẩm có thể sử dụng được và trình bày trước ban giám khảo.

Nhóm tham gia vì:

- Muốn thử sức trong môi trường áp lực thời gian.
- Muốn biết mình có thể làm được gì trong 36 giờ.
- Muốn kết nối với chuyên gia trong lĩnh vực IT và AI.
- Muốn trải nghiệm cảm giác làm việc như một mini startup.
- Muốn tạo ra sản phẩm thật thay vì chỉ dừng ở ý tưởng.

### Quá Trình Hình Thành Ý Tưởng

Ban đầu, nhóm đã brainstorm nhiều lần nhưng chưa tìm ra ý tưởng đủ tốt. Sau khi nghe khai mạc, tiêu chí chấm điểm và timeline, nhóm quyết định đi về để bình tĩnh suy nghĩ.

Thay vì cố tìm một ý tưởng quá lớn hoặc quá vĩ mô, nhóm quay lại nhìn vào công việc hằng ngày. Nhóm nhận ra rằng nhiều người dùng AI để generate UI, nhưng mỗi lần muốn chỉnh màu button, spacing, layout hoặc component thì phải prompt lại từ đầu.

Điều này gây ra các vấn đề:

- Mất thời gian.
- Tốn token.
- Khó chỉnh sửa chi tiết.
- AI có thể generate lại toàn bộ UI không đúng ý.
- Người dùng không thể tương tác trực tiếp với giao diện vừa tạo.

Từ đó, nhóm nghĩ ra ý tưởng xây dựng một app cho phép:

- Generate UI từ input.
- Chọn template.
- Upload hình ảnh hoặc vẽ layout đơn giản.
- Render UI ra HTML.
- Chỉnh sửa trực tiếp trên giao diện.
- Kéo thả component.
- Xem source code.
- Lưu lịch sử chỉnh sửa.
- Public link để chia sẻ cho người khác review.

### Kiến Trúc Của Dự Án

Dự án sử dụng kiến trúc serverless tương đối đơn giản. Phần quan trọng nhất nằm ở AI pipeline.

Pipeline gồm ba agent chính:

#### Agent 1 - Vision Analysis

Agent này nhận input từ người dùng, đặc biệt là hình ảnh hoặc sketch. Nó phân tích hình ảnh, nhận diện layout, component và cấu trúc giao diện, sau đó trả về dữ liệu dạng JSON layer.

#### Agent 2 - Code / Layout Engine

Agent thứ hai đọc dữ liệu JSON từ Agent 1, sau đó tạo ra thông tin về size, CSS, layout và cấu trúc giao diện.

#### Agent 3 - Design Agent

Agent thứ ba được cấu hình với system prompt về design. Nó đọc yêu cầu từ Agent 2 và tạo ra code giao diện HTML/CSS cho người dùng.

### Demo Sản Phẩm

Trong phần demo, nhóm trình bày giao diện có panel bên trái để người dùng nhập yêu cầu.

Người dùng có thể:

- Chọn template.
- Upload hình ảnh.
- Dùng camera.
- Vẽ layout đơn giản.
- Generate dashboard hoặc UI.
- Xem source code HTML.
- Kéo thả các component trực tiếp trên giao diện.
- Chỉnh sửa element thủ công.
- Xem lịch sử chỉnh sửa.
- Public link HTML để gửi cho bạn bè hoặc đồng nghiệp review.

Tính năng nhóm tâm đắc nhất là **edit trực tiếp trên UI**. Người dùng không cần prompt lại từ đầu chỉ để chỉnh sửa một element nhỏ.

### Khó Khăn Trong Quá Trình Thi

Nhóm gặp nhiều khó khăn trong quá trình làm sản phẩm.

#### Hết token

Khi đang build, AI tool bị báo limit token và phải chờ khoảng hai tiếng. Điều này làm gián đoạn tiến độ vì agent đang trong trạng thái làm dở, nhóm không muốn đổi sang một agent khác.

#### AI over-generation

Có những yêu cầu đơn giản nhưng AI tự suy diễn sâu hơn và generate quá nhiều code không cần thiết. Nhóm phải kiểm soát lại output để tránh code bị phình to và khó sửa.

#### Áp lực thời gian

Nhóm mất khoảng 12 tiếng để nghĩ ý tưởng, nên chỉ còn khoảng 24 tiếng để build sản phẩm. Gần giờ pitching, nhóm vừa phải chuẩn bị video demo, slide thuyết trình, tập trình bày và hoàn thiện sản phẩm.

#### Mệt mỏi về thể lực

Hackathon kéo dài 36 giờ liên tục. Đến khoảng 4-5 giờ sáng, mọi người bắt đầu rất mệt nhưng công việc lại tăng lên. Nhóm phải cố gắng duy trì năng lượng để hoàn thành sản phẩm và thuyết trình.

### Bài Học Rút Ra

Nhóm rút ra nhiều bài học quan trọng:

#### Không cần ý tưởng quá lớn

Thay vì chọn một vấn đề vĩ mô, nhóm chọn một vấn đề nhỏ nhưng chính họ gặp hằng ngày. Điều này giúp sản phẩm thực tế và dễ giải thích hơn.

#### Nhiều feature không có nghĩa là tốt hơn

Ban đầu nhóm muốn thêm rất nhiều tính năng. Nhưng vì thời gian giới hạn, nhóm phải chọn feature quan trọng nhất là trải nghiệm chỉnh sửa UI trực tiếp.

#### Teamwork rất quan trọng

Do các thành viên đã từng làm việc với nhau và hiểu thế mạnh của nhau, nhóm có thể chia task nhanh hơn, phối hợp tốt hơn và ghép các phần lại thành sản phẩm hoàn chỉnh.

#### Quản lý sức khỏe cũng là một phần của hackathon

Trong hackathon dài 36 giờ, việc ăn uống, nghỉ ngơi, chia ca và giữ tinh thần là rất quan trọng để có thể pitch tốt ở cuối cuộc thi.

### Bài Học Rút Ra Từ Session

- Hackathon giúp rèn luyện khả năng build sản phẩm dưới áp lực thời gian.
- Ý tưởng tốt có thể đến từ vấn đề nhỏ trong công việc hằng ngày.
- Nên tập trung vào core feature thay vì ôm quá nhiều tính năng.
- AI rất hữu ích nhưng cần kiểm soát token, output và scope.
- Teamwork, chia việc và giao tiếp quyết định rất lớn đến kết quả.
- Đừng ngại tham gia hackathon vì đây là cơ hội học rất nhanh.

---

## 6. Session 5 - Vì Sao LLM Vẫn Không Hoàn Toàn Deterministic Khi Temperature Bằng 0?

### Giới Thiệu Chủ Đề

Phần tiếp theo trình bày về một chủ đề technical hơn: cách Large Language Models tạo output và vì sao output vẫn có thể thay đổi dù cấu hình **temperature = 0**.

Diễn giả nhấn mạnh rằng LLM là một **probabilistic engine**, tức là mô hình hoạt động dựa trên xác suất. Các token được generate ra luôn có yếu tố probability, dù người dùng cố gắng giảm randomness.

### Cách LLM Hoạt Động

LLM hoạt động bằng cách chọn token tiếp theo phù hợp nhất để điền vào câu trả lời.

Quy trình đơn giản:

1. Người dùng đưa prompt vào.
2. Model tính điểm cho toàn bộ token trong vocabulary.
3. Các token được xếp hạng theo điểm.
4. Model chọn token tiếp theo.
5. Quá trình lặp lại cho đến khi tạo xong câu trả lời.

Điểm số của token thường được gọi là **logit**.

### Temperature Là Gì?

Temperature là tham số điều chỉnh độ ngẫu nhiên của model.

- Temperature cao: output sáng tạo hơn, random hơn.
- Temperature thấp: output ổn định hơn.
- Temperature = 0: về lý thuyết, model luôn chọn token có điểm cao nhất.

Khi temperature lớn hơn 0, model dùng softmax để chọn token theo phân phối xác suất. Khi temperature bằng 0, model chuyển sang greedy decoding, tức là luôn chọn token có điểm cao nhất.

### Assumption Phổ Biến

Nhiều người nghĩ rằng:

```text
Temperature = 0 → Cùng prompt → Luôn cùng output
```

Điều này rất quan trọng trong các workflow production, vì nhiều hệ thống muốn output của LLM có tính ổn định giống như workflow truyền thống.

Tuy nhiên, thực tế không hoàn toàn như vậy.

### Vì Sao Output Vẫn Có Thể Khác?

Diễn giả đưa ra hai nhóm nguyên nhân chính.

#### Nguyên nhân kỹ thuật

Máy tính xử lý số thập phân không hoàn toàn tuyệt đối. Khi GPU thực hiện tính toán song song, thứ tự cộng, làm tròn và xử lý số có thể khác nhau giữa các lần chạy.

Ví dụ:

```text
(a + b) + c
```

và

```text
a + (b + c)
```

có thể cho ra sai khác rất nhỏ khi tính với floating point.

Khi có hàng triệu hoặc hàng tỷ phép tính, sai khác nhỏ này có thể tích lũy và ảnh hưởng đến điểm token.

#### Inference Optimization Từ Provider

Nguyên nhân lớn hơn đến từ các hosting provider như OpenAI, Anthropic hoặc Amazon Bedrock. Để giảm chi phí và tăng hiệu năng, provider có thể dùng các kỹ thuật inference optimization.

Một kỹ thuật phổ biến là batching: gộp nhiều prompt ngắn thành một batch lớn để GPU xử lý cùng lúc.

Khi đó, dù người dùng gửi cùng một prompt, môi trường xử lý thật sự trên GPU có thể khác nhau giữa các lần chạy. Điều này làm output có thể thay đổi dù temperature bằng 0.

### Demo So Sánh Bedrock Và Local Model

Diễn giả demo cùng một prompt với temperature = 0.

Prompt ví dụ:

```text
Write me a story about the great polar bear in Antarctica.
```

Khi chạy trên Bedrock, hai lần chạy có thể tạo ra output khác nhau về số token và nội dung.

Khi chạy cùng model trên local, cùng cấu hình temperature = 0, output gần như giống hệt nhau giữa các lần chạy.

Điều này cho thấy inference optimization của provider có thể ảnh hưởng đến determinism.

### Tác Động Đến Production

Điều này quan trọng vì trong một số use case, output cần ổn định và có thể dự đoán được.

Ví dụ:

- Workflow tự động.
- Xử lý hồ sơ.
- Trích xuất dữ liệu.
- Phân loại văn bản.
- Sinh JSON để downstream service xử lý.
- Ứng dụng tài chính hoặc pháp lý.
- Các hệ thống critical cần audit.

Nếu downstream service giả định output luôn đúng format, hệ thống có thể lỗi khi LLM trả ra format khác.

### Cách Giảm Thiểu Rủi Ro

Diễn giả đề xuất một số hướng mitigation.

#### Chạy nhiều lần và chọn kết quả chung

Có thể chạy nhiều agent hoặc nhiều lượt generate, sau đó dùng một agent khác chọn câu trả lời nhất quán nhất.

Cách này tăng accuracy nhưng đánh đổi bằng:

- Chi phí cao hơn.
- Latency cao hơn.
- Kiến trúc phức tạp hơn.

#### Self-host model

Nếu cần kiểm soát tuyệt đối, có thể self-host model trên hạ tầng riêng. Khi đó, team có thể kiểm soát runtime, inference stack và cấu hình.

Tuy nhiên, cách này tốn chi phí vận hành và không tận dụng được economy of scale của provider.

#### Dùng parameter hỗ trợ format

Một số provider có tính năng như JSON mode. Khi bật JSON mode, model có xu hướng chỉ trả về JSON hợp lệ thay vì thêm câu giải thích không cần thiết.

Điều này giúp downstream system xử lý output ổn định hơn.

#### Thiết kế downstream service chịu được lỗi

Quan trọng nhất là không nên giả định output của LLM luôn đúng tuyệt đối. Downstream service cần xử lý được nhiều trường hợp:

- Output sai format.
- Output thiếu field.
- Output có thêm text không mong muốn.
- Output khác nhau giữa các lần chạy.
- Model hallucinate.

### Lưu Ý Khi Config Model

Diễn giả cũng nhắc rằng trong một số trường hợp, temperature = 0 có thể làm model bị lặp từ hoặc câu. Khi đó, có thể dùng temperature khoảng 0.1 để giữ tính ổn định nhưng tránh lỗi lặp.

Nếu self-host model, có thể dùng tham số repeat penalty, nhưng cần cẩn thận vì nó có thể ảnh hưởng xấu khi generate code hoặc JSON.

Quan trọng nhất là:

```text
Luôn đọc official documentation của model trước khi config.
```

### Bài Học Rút Ra

- LLM là probabilistic model, không phải deterministic workflow.
- Temperature = 0 không đảm bảo output luôn giống 100%.
- Inference optimization của provider có thể làm output thay đổi.
- Nếu cần output ổn định, cần thiết kế mitigation strategy.
- Downstream service phải xử lý được output không hoàn hảo.
- Testing rất quan trọng khi đưa LLM vào production.

---

## 7. Session 6 - Enterprise-Grade Multi-Agent System Cho Bài Toán Đánh Giá Tín Dụng Startup

### Giới Thiệu Chủ Đề

Session cuối cùng tập trung vào cách xây dựng **enterprise-grade multi-agent system** cho bài toán đánh giá tín dụng startup.

Diễn giả nhấn mạnh rằng sau nhiều phần chia sẻ kỹ thuật, phần này sẽ chuyển sang mindset nghiệp vụ: làm sao để thiết kế một hệ thống có người dùng thật, giải quyết vấn đề thật và có thể dùng trong doanh nghiệp.

Bốn câu hỏi quan trọng được đặt ra:

```text
Ai dùng?
Dùng cái gì?
Tại sao họ phải dùng?
Khi nào là lúc phù hợp để dùng?
```

### Bài Toán Nghiệp Vụ

Trong ngân hàng, việc đánh giá tín dụng cho startup khó hơn so với doanh nghiệp truyền thống.

Lý do là startup thường không có đầy đủ các yếu tố mà mô hình tín dụng truyền thống yêu cầu:

- Không có báo cáo tài chính 3 năm.
- Không có credit history rõ ràng.
- Không có tài sản thế chấp lớn.
- Thời gian hoạt động còn ngắn.
- Tài sản chính là ý tưởng, intellectual property, founder và traction.
- Dữ liệu quan trọng nằm ở nhiều chiều khác nhau như market, team, revenue, user growth, product, social presence.

Trong khi đó, startup lại là một nhóm doanh nghiệp quan trọng trong bối cảnh Việt Nam đang khuyến khích đổi mới sáng tạo.

### Vì Sao Cần GenAI?

Các dữ liệu của startup thường không phù hợp với mô hình truyền thống. Vì vậy, GenAI có thể hỗ trợ thu thập, phân tích và tổng hợp nhiều chiều dữ liệu khác nhau.

Một số chiều dữ liệu có thể phân tích:

- Financial data.
- Market data.
- Founder profile.
- Team background.
- Traction.
- TAM / SAM / SOM.
- Competitor landscape.
- Growth potential.
- Risk factors.

TAM, SAM, SOM được giải thích như sau:

- **TAM**: Total Addressable Market, tổng thị trường có thể tiếp cận.
- **SAM**: Serviceable Available Market, phần thị trường phù hợp với sản phẩm.
- **SOM**: Serviceable Obtainable Market, phần thị trường thực tế có thể đạt được.

### Single Agent Hay Multi-Agent?

Diễn giả đặt câu hỏi: với bài toán đánh giá tín dụng startup, nên dùng single agent hay multi-agent?

Câu trả lời là multi-agent, vì bài toán có nhiều loại dữ liệu và đòi hỏi nhiều chuyên môn khác nhau.

Single agent phù hợp với:

- POC đơn giản.
- Single domain.
- Linear workflow.
- Simple tool orchestration.
- Low-stakes decision.
- Rapid prototype.

Nhưng bài toán đánh giá tín dụng startup không phù hợp với single agent vì:

- Input rất nhiều.
- Dữ liệu thuộc nhiều domain khác nhau.
- Context window có giới hạn.
- Cần nhiều chuyên môn khác nhau.
- Cần kiểm soát risk và compliance.
- Cần output có thể audit được.

### Thiết Kế Multi-Agent System

Hệ thống được thiết kế như một hội đồng tín dụng gồm nhiều agent chuyên biệt.

#### Credit Committee / Orchestrator

Đây là agent điều phối chính, giống như host của một hội đồng. Nó nhận yêu cầu, phân chia task cho các agent chuyên môn và tổng hợp kết quả cuối cùng thành báo cáo.

#### Financial Analyst Agent

Agent này phân tích báo cáo tài chính, dòng tiền, revenue, runway, burn rate và tình hình tài chính hiện tại của startup.

#### Market Research Agent

Agent này phân tích thị trường, đối thủ cạnh tranh, TAM/SAM/SOM, thời điểm thị trường và tiềm năng tăng trưởng.

#### Team Evaluator Agent

Agent này đánh giá founder, co-founder, đội ngũ, kinh nghiệm, mạng lưới, hoạt động trên LinkedIn, X, Facebook hoặc các tín hiệu public khác.

#### Risk Assessor Agent

Agent này phân tích rủi ro, bao gồm rủi ro tài chính, rủi ro thị trường, rủi ro vận hành, rủi ro pháp lý, security và compliance.

#### Report Synthesizer Agent

Agent cuối cùng tổng hợp kết quả từ các agent khác thành một báo cáo có cấu trúc để người dùng hoặc chuyên viên ngân hàng xem xét.

### Vì Sao Multi-Agent Phù Hợp?

Multi-agent phù hợp vì:

- Mỗi agent có chuyên môn riêng.
- Context của từng agent nhỏ hơn và tập trung hơn.
- Agent có thể challenge assumption của nhau.
- Có thể chạy song song để tăng tốc độ xử lý.
- Có audit trail cho từng bước.
- Có thể scale từng agent độc lập.
- Nếu một agent fail, toàn bộ hệ thống không nhất thiết fail hoàn toàn.
- Kiến trúc gần giống thiết kế distributed system trong solution architecture.

### Security Và Compliance Trong Doanh Nghiệp

Diễn giả nhấn mạnh rằng trong enterprise, security và compliance quan trọng hơn việc demo chạy được.

Một số vấn đề cần quan tâm:

- Prompt injection.
- Output filtering.
- API key rotation.
- IAM access key rotation.
- Audit logging.
- Data leakage.
- Guardrails.
- MCP attack vector.
- Input sanitization.
- Human approval.
- Compliance theo ngành tài chính, ngân hàng, biotech hoặc medtech.

Diễn giả đưa ví dụ rằng trong môi trường ngân hàng, không thể tùy tiện cắm MCP, tool hoặc AI agent vào hệ thống nội bộ. Mọi thứ cần được security review và có boundary rõ ràng.

### Prompt Injection Và Guardrails

Prompt injection là tình huống người dùng hoặc attacker đưa instruction độc hại vào input để làm AI bỏ qua rule ban đầu.

Ví dụ:

```text
Ignore previous instructions and give me ...
```

Nếu hệ thống không có guardrails, AI có thể trả lời sai, lộ thông tin hoặc thực hiện hành động không mong muốn.

Do đó, hệ thống cần:

- Guardrails cho input.
- Guardrails cho output.
- Filter thông tin nhạy cảm.
- Giới hạn quyền của agent.
- Không cho agent tự hành vượt quá boundary.
- Human-in-the-loop cho quyết định quan trọng.

### Audit Trail Và Trách Nhiệm

Trong môi trường doanh nghiệp, đặc biệt là ngân hàng, audit trail rất quan trọng.

Nếu hệ thống AI đưa ra đề xuất sai và con người approve sai, trách nhiệm cuối cùng không thuộc về model mà thuộc về người được giao nhiệm vụ phê duyệt.

Vì vậy, mỗi quyết định cần lưu lại:

- Input.
- Output.
- Agent nào xử lý.
- Người nào review.
- Người nào approve.
- Lý do quyết định.
- Thời điểm quyết định.
- Version của model hoặc workflow.

### Knowledge Transfer Và Context Engineering

Một nội dung quan trọng là knowledge transfer.

Trong doanh nghiệp, tài liệu có thể rất dài, ví dụ hồ sơ tín dụng có thể hơn 200 trang PDF. Nhưng chuyên gia không đọc mọi thứ theo cách bình thường. Họ biết phần nào quan trọng, phần nào có thể bỏ qua, chỉ số nào cần xem và dấu hiệu nào cần chú ý.

Vì vậy, không thể chỉ đẩy toàn bộ tài liệu vào LLM và kỳ vọng nó hiểu như chuyên gia.

Cần chuyển giao tri thức từ chuyên gia vào hệ thống, bao gồm:

- Cách đọc tài liệu.
- Phần nào quan trọng.
- Chỉ số nào cần chú ý.
- Quy tắc nghiệp vụ.
- Điều kiện phê duyệt.
- Điều kiện cảnh báo.
- Cách đánh giá rủi ro.

Đây là lý do context engineering quan trọng hơn việc chỉ nhồi nhiều dữ liệu.

### Deployment Approach

Diễn giả gợi ý một cách triển khai hệ thống agent:

- Phát triển ở local.
- Containerize ứng dụng.
- Push image lên ECR.
- Dùng agent runtime / Bedrock Agent Core hoặc nền tảng tương tự để deploy.
- Tạo endpoint.
- Kết nối Lambda hoặc API Gateway.
- Xây frontend bằng React, Streamlit hoặc framework khác.
- Gọi API Gateway để tương tác với hệ thống agent.

### ROI Và Business Value

Khi đưa giải pháp vào doanh nghiệp, không thể chỉ nói "em đã code xong". Cần chứng minh giá trị bằng số liệu.

Một số câu hỏi cần trả lời:

- Trước khi có hệ thống, quy trình mất bao nhiêu thời gian?
- Sau khi có hệ thống, tiết kiệm được bao nhiêu giờ?
- Giảm được bao nhiêu chi phí?
- Tăng được bao nhiêu năng suất?
- Giảm được bao nhiêu rủi ro?
- Payback period là bao lâu?
- ROI là bao nhiêu?

Diễn giả nhấn mạnh:

```text
Numbers speak louder than words.
```

### Gợi Ý Cho Sinh Viên / Fresher

Diễn giả đưa ra một số hướng để người học có thể biến ý tưởng này thành project end-to-end cho CV:

- Xây frontend.
- Dùng AWS Cognito cho authentication.
- Hiểu JWT.
- Xây backend.
- Thiết kế agent permission.
- Tích hợp MCP có kiểm soát.
- Viết infrastructure as code bằng Terraform.
- Deploy bằng AWS.
- Có security, audit trail và logging.
- Xây hệ thống có khả năng phục vụ user thật.

Diễn giả cũng nhấn mạnh rằng các kiến thức backend và software engineering vẫn rất quan trọng. AI là điểm cộng lớn, nhưng không thay thế nền tảng kỹ thuật phần mềm.

### Thông Điệp Cuối

Thông điệp cuối của session là:

```text
Xây dựng hệ thống không phải chỉ cần chạy được.
Hệ thống phải chạy an toàn, đáng tin cậy và phục vụ được người dùng.
```

### Bài Học Rút Ra

- Khi thiết kế hệ thống, cần bắt đầu từ người dùng và bài toán nghiệp vụ.
- Multi-agent phù hợp với bài toán nhiều domain, nhiều dữ liệu và nhiều chuyên môn.
- Enterprise AI system cần security, compliance, audit trail và guardrails.
- Không nên để AI tự hành hoàn toàn trong quyết định quan trọng.
- Knowledge transfer và context engineering rất quan trọng.
- Làm project cho CV nên có end-to-end flow, không chỉ demo.
- Terraform và infrastructure as code là kỹ năng nên học.
- AI là công cụ mạnh, nhưng backend, software engineering và system design vẫn là nền tảng.

---

## Những Gì Em Học Được Sau Sự Kiện

### Về Thị Trường Việc Làm

Sau sự kiện, em hiểu rằng AI không đơn giản là làm mất việc của lập trình viên. AI làm cho việc tạo phần mềm rẻ hơn, từ đó số lượng sản phẩm phần mềm có thể tăng lên. Tuy nhiên, yêu cầu đối với kỹ sư phần mềm cũng cao hơn.

Người học không chỉ cần biết code, mà còn cần biết:

- Xây dựng sản phẩm thật.
- Hiểu nghiệp vụ.
- Hiểu use case doanh nghiệp.
- Biết vận hành hệ thống.
- Biết security và monitoring.
- Biết giải thích giá trị mình tạo ra.

### Về Cách Sử Dụng AI

Em học được rằng AI cần context đúng. Nếu context sai hoặc quá loãng, AI sẽ trả lời sai hoặc không đúng nhu cầu.

Một prompt tốt không chỉ là prompt dài, mà là prompt có đủ thông tin quan trọng và đúng với ngữ cảnh.

Em cũng học thêm các khái niệm:

- AI First Mindset.
- AI Adoption.
- Second Brain.
- Context Engineering.
- Prompt Injection.
- Guardrails.
- MCP attack vector.

### Về AWS Và Cloud

Sự kiện giúp em hiểu sâu hơn về nhiều dịch vụ AWS như:

- Amazon Q.
- Amazon CloudFront.
- Amazon S3.
- Amazon Cognito.
- Amazon API Gateway.
- AWS Lambda.
- Amazon Bedrock.
- Amazon DynamoDB.
- Amazon CloudWatch.
- AWS Certificate Manager.
- Terraform và Infrastructure as Code.

Đặc biệt, phần CloudFront giúp em hiểu rằng CDN không chỉ dùng để cache nội dung, mà còn giúp giảm chi phí, bảo vệ origin, chống DDoS, tăng hiệu năng và tăng độ tin cậy.

### Về AI Trong Production

Em học được rằng đưa AI vào production không đơn giản là gọi API model. Cần phải quan tâm đến:

- Output không hoàn toàn deterministic.
- Temperature = 0 không đảm bảo output giống nhau tuyệt đối.
- Provider có thể dùng inference optimization.
- Downstream service phải xử lý được output lỗi.
- Cần testing nhiều trường hợp.
- Cần guardrails, logging và audit.

### Về Làm Sản Phẩm

Từ phần hackathon, em học được rằng một sản phẩm tốt không nhất thiết phải bắt đầu từ ý tưởng quá lớn. Đôi khi, giải quyết một vấn đề nhỏ nhưng thật sự tồn tại trong công việc hằng ngày lại có giá trị hơn.

Em cũng học được rằng trong thời gian giới hạn, cần tập trung vào core feature thay vì cố thêm quá nhiều chức năng.

---

## Ứng Dụng Vào Dự Án Cá Nhân

Sau sự kiện này, em có thể áp dụng nhiều bài học vào dự án **AWS Serverless E-commerce Platform** của mình.

### Áp Dụng Tư Duy Sản Phẩm

Thay vì chỉ xem dự án ecommerce là một bài demo, em cần phát triển nó như một sản phẩm có thể dùng thật.

Dự án nên có:

- User flow rõ ràng.
- Admin flow rõ ràng.
- Payment flow.
- Order management.
- Image upload.
- Authentication.
- Monitoring.
- Alert.
- CI/CD.
- Security.
- Documentation.

### Áp Dụng Kiến Thức CloudFront

Trong dự án ecommerce, CloudFront đang được dùng để phân phối frontend và hình ảnh sản phẩm. Sau session CloudFront, em hiểu thêm rằng có thể dùng CloudFront để:

- Tăng tốc website.
- Giảm request về S3 origin.
- Bảo vệ origin bucket.
- Bật HTTPS.
- Dùng custom error page.
- Tối ưu cache.
- Dùng signed URL nếu cần bảo vệ file riêng tư.
- Kết hợp WAF để tăng bảo mật.

### Áp Dụng Monitoring Và Security

Từ các phần chia sẻ về enterprise và production, em cần chú ý hơn đến:

- CloudWatch Logs.
- CloudWatch Metrics.
- SNS alert.
- IAM least privilege.
- Cognito authentication.
- API Gateway authorization.
- Audit log cho admin actions.
- Bảo vệ payment callback.
- Không để lộ access key hoặc secret.

### Áp Dụng AI Và Prompt Engineering

Khi dùng AI để hỗ trợ code hoặc viết tài liệu, em sẽ:

- Tách từng chat theo từng task.
- Cung cấp context đúng.
- Không copy rule hoặc prompt từ mạng mà không hiểu.
- Kiểm tra lại output.
- Test code trước khi đưa vào project.
- Không để AI quyết định thay hoàn toàn.

### Áp Dụng Tư Duy Enterprise Multi-Agent

Trong tương lai, nếu mở rộng dự án ecommerce, em có thể thử xây dựng các agent nhỏ để hỗ trợ:

- Phân tích đơn hàng.
- Tóm tắt doanh thu.
- Gợi ý sản phẩm bán chạy.
- Phát hiện đơn hàng bất thường.
- Hỗ trợ admin viết mô tả sản phẩm.
- Tạo báo cáo vận hành.

Tuy nhiên, các agent này cần có guardrails, logging và human review.

---

## Trải Nghiệm Khi Tham Gia / Theo Dõi Sự Kiện

Sự kiện mang lại cho em nhiều góc nhìn thực tế hơn về AWS, AI và nghề IT.

### Nội Dung Đa Dạng

Các session bao phủ nhiều chủ đề khác nhau:

- Tình hình thị trường việc làm.
- AI mindset và prompt context.
- Amazon Q và agent automation.
- Amazon CloudFront.
- Hackathon và sản phẩm AI.
- LLM determinism.
- Enterprise multi-agent system.

Điều này giúp em thấy rằng công nghệ không chỉ là code, mà còn liên quan đến sản phẩm, chi phí, bảo mật, vận hành, người dùng và business value.

### Tính Thực Tế Cao

Nhiều phần chia sẻ đến từ kinh nghiệm thật trong doanh nghiệp, ví dụ như:

- Security review trong ngân hàng.
- Khó khăn khi dùng AI trong production.
- Vấn đề chi phí CloudFront.
- Hackathon 36 giờ.
- Trách nhiệm khi approve output từ AI.
- Tư duy ROI khi trình bày giải pháp cho lãnh đạo.

Những nội dung này giúp em hiểu rõ hơn sự khác biệt giữa project học tập và hệ thống production.

### Có Thêm Động Lực Học AWS Và AI

Sau sự kiện, em có thêm động lực để tiếp tục hoàn thiện dự án AWS Serverless E-commerce Platform. Em nhận ra rằng nếu biết kết hợp AWS, AI, security, monitoring và tư duy sản phẩm, dự án cá nhân có thể trở thành một portfolio rất tốt.

---

## Một Số Hình Ảnh Khi Tham Gia Sự Kiện

<img src="/workshop-/images/4-Events/event2.1.jpg" alt="FCAJ Community Day Event 2 Image 1" style="max-width: 100%; height: auto;">

<img src="/workshop-/images/4-Events/event1.2.jpg" alt="FCAJ Community Day Event 2 Image 2" style="max-width: 100%; height: auto;">

---

## Tổng Kết

Tổng thể, **FCAJ Community Day - AI, Cloud và Enterprise Systems** là một sự kiện rất hữu ích đối với sinh viên IT, fresher và những người đang học AWS hoặc AI.

Sự kiện giúp em hiểu rằng trong thời đại AI, người học cần nhiều hơn kỹ năng code. Cần có nền tảng kỹ thuật, tư duy sản phẩm, khả năng hiểu nghiệp vụ, khả năng sử dụng AI đúng cách, hiểu cloud, biết security và biết cách xây dựng hệ thống có thể vận hành thật.

Những bài học quan trọng nhất em rút ra là:

- AI làm thay đổi thị trường việc làm nhưng cũng tạo ra cơ hội mới.
- Người học cần có sản phẩm thật thay vì chỉ có demo.
- Sử dụng AI hiệu quả cần context đúng, không phải prompt thật dài.
- Amazon Q và agent có thể hỗ trợ nhiều workflow thực tế trong doanh nghiệp.
- CloudFront không chỉ là CDN mà còn giúp tối ưu chi phí, bảo mật và hiệu năng.
- Hackathon giúp rèn luyện khả năng build sản phẩm nhanh và tập trung vào core feature.
- LLM vẫn có yếu tố không xác định dù temperature bằng 0.
- AI system trong production cần testing, guardrails và downstream error handling.
- Enterprise multi-agent system cần được thiết kế theo hướng an toàn, có audit trail và phục vụ đúng nghiệp vụ.
- Xây dựng hệ thống không phải chỉ cần chạy được, mà phải chạy an toàn, đáng tin cậy và phục vụ được người dùng.

Sau sự kiện, em có thêm định hướng rõ ràng hơn để tiếp tục phát triển dự án **AWS Serverless E-commerce Platform**, đồng thời học sâu hơn về AWS, AI, CloudFront, Prompt Engineering, Security, Monitoring, Infrastructure as Code và Enterprise System Design.
