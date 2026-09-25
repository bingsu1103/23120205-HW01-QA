# Hướng dẫn thực hiện HW01 - QA/QC Jobs, Software Defects và Physical Product

> Nguồn yêu cầu: `2026.HW01.Jobs.Defects.PhysicalProduct_En.pdf` (7 trang).
>
> Deadline dùng trong hướng dẫn: **13:00 ngày 28/09/2026**, múi giờ `Asia/Ho_Chi_Minh`.
>
> Hình thức: bài cá nhân; nộp báo cáo trên Moodle và cung cấp liên kết GitHub repository.

## 1. Mục tiêu và nguyên tắc bắt buộc

Tài liệu này hướng dẫn làm đúng các đầu việc đề bài yêu cầu, không tự bổ sung deliverable ngoài rubric. Mọi số liệu, ảnh chụp, video, kết quả thực thi và khai báo sử dụng AI phải phản ánh đúng công việc thực tế của sinh viên.

Các nguyên tắc không được vi phạm:

1. Không tạo hoặc chỉnh sửa bằng AI các bằng chứng cá nhân: ảnh thiết bị cùng thẻ sinh viên, video thực thi có giọng nói, ảnh job posting có tài khoản đăng nhập và prompt log.
2. Không tạo prompt log giả, không lùi timestamp và không ghi một prompt chưa từng gửi như thể đã dùng thật.
3. Nếu thiếu log của một thao tác cũ, chọn một trong hai cách:
   - chạy lại prompt ở thời điểm hiện tại và ghi timestamp thật; hoặc
   - ghi rõ `RECONSTRUCTED - not an original audit event` và không trình bày nó như log gốc.
4. Không đưa ảnh thẻ sinh viên, form đã ký, serial chưa che, credential hoặc bằng chứng riêng tư lên repository công khai.
5. Không bịa defect, Actual Result, Verdict, salary, ngày đăng tuyển hoặc kết quả test.
6. Tất cả AI-generated artifacts phải có AI Audit Report theo đúng mẫu 5 phần của đề.

Theo đề bài, khai báo AI sai có thể khiến bài nhận điểm 0 và bị chuyển xử lý kỷ luật. Vì vậy, phần AI log trong hướng dẫn này ưu tiên khả năng kiểm chứng, không ưu tiên làm log trông “đẹp”.

## 2. Mốc thời gian và quy tắc chọn job

- Deadline: `13:00 28/09/2026`.
- Mốc đúng 60 ngày: `13:00 30/07/2026`.
- Nếu job posting có cả ngày và giờ: chỉ chấp nhận khi thời điểm đăng không sớm hơn mốc trên.
- Nếu job posting chỉ hiện ngày, không hiện giờ: chọn từ **31/07/2026** trở đi để tránh tranh cãi ở biên 60 ngày.
- Không dùng các nhãn tương đối như `30+ days ago` làm bằng chứng duy nhất. Phải tìm được ngày cụ thể trên trang tuyển dụng, trang công ty hoặc nguồn đáng tin cậy khác.
- Kiểm tra lại trạng thái job trước khi chụp. Job đã đóng hoặc bị gỡ không nên dùng nếu không còn đủ nội dung để đối chiếu.

## 3. Bảng kiểm deliverable bắt buộc

Trạng thái ban đầu của mọi dòng là `NOT STARTED`. Chỉ đổi thành `PASS` sau khi đạt điều kiện ở cột cuối.

| ID | Yêu cầu | Bằng chứng bắt buộc | Nơi lưu đề xuất | Trạng thái | Điều kiện PASS |
|---|---|---|---|---|---|
| SETUP-01 | Xác nhận deadline, StudentID và quy định nộp | Ảnh/trang Moodle có deadline; StudentID dùng thống nhất | `private-evidence/submission/` | NOT STARTED | Deadline và tên file ZIP đã được khóa |
| FORM-01 | AI-06 Student Acknowledgement | Mẫu được ký theo yêu cầu môn học | `private-evidence/signed-forms/` | NOT STARTED | AI-06 hợp lệ trước khi bài AI-assisted được chấm |
| G9.1-01 | AI tạo mindmap QA/QC role trong ISTQB process | Full prompt, full output hoặc ảnh output gốc | `ai/mindmap/ai-original.png` và `ai/prompt-log.md` | NOT STARTED | Có output AI nguyên bản và timestamp thật |
| G9.1-02 | Sinh viên tìm và sửa 3 lỗi trong mindmap | Danh sách 3 lỗi, căn cứ ISTQB/course slides, mindmap đã sửa | `ai/mindmap/corrected-mindmap.md` | NOT STARTED | Đủ đúng 3 lỗi cụ thể, có căn cứ và phần sửa |
| R1-01 | 10 job QA/QC trong 60 ngày | 10 record và 10 ảnh có tài khoản đăng nhập | `job-market/job-postings.md`; ảnh trong `private-evidence/jobs/` | NOT STARTED | Đủ `JOB-01..JOB-10`, mỗi record và ảnh đều đạt checklist |
| R1-02 | Ít nhất 3 job yêu cầu AI/LLM/AI automation | Câu yêu cầu AI nhìn thấy trong JD/ảnh | Cùng record `JOB-*` tương ứng | NOT STARTED | Có ít nhất 3 job với bằng chứng AI rõ ràng, không suy diễn |
| R1-03 | AI Impact Analysis cho mỗi job | 1-2 câu do sinh viên đánh giá cho từng job | `job-market/job-postings.md` | NOT STARTED | Đủ 10/10 phân tích và gắn đúng job |
| R2-01 | 20 software defects publicized trong 2022-2026 | Link nguồn và record chi tiết | `defects/software-defects.md` | NOT STARTED | Đủ `DEF-01..DEF-20`, nguồn và năm hợp lệ |
| R2-02 | Ít nhất 5 defect liên quan AI/LLM | Nhãn AI-related và nguồn chứng minh | Record `DEF-*` tương ứng | NOT STARTED | Có ít nhất 5 record liên quan hallucination, prompt injection, bias hoặc lỗi AI/LLM tương đương |
| R2-03 | Một quan sát AI bias/hallucination cho mỗi defect | Full AI output, câu/ý bị đánh dấu, giải thích và correction | `ai/ai-audit-report.md`; bằng chứng trong `private-evidence/defects/` | NOT STARTED | Đủ 20/20 defect có một nhận xét cụ thể, kiểm chứng được |
| R3-01 | Chọn một thiết bị vật lý cụ thể | Brand, model, year, serial đã che 4 ký tự giữa | `physical-product/device-profile.md` | NOT STARTED | Thiết bị xác định được, không phải sản phẩm phần mềm |
| R3-02 | Ảnh thiết bị và thẻ sinh viên trong cùng khung hình | Ảnh thật do sinh viên tự chụp | `private-evidence/device/DEVICE-ID.jpg` | NOT STARTED | Một ảnh thấy đồng thời thiết bị và thẻ sinh viên |
| R3-03 | 15 test cases | Objective, Input, Steps, Expected, Actual, Verdict | `physical-product/HW01_Test_Workbook.xlsx` | NOT STARTED | Đúng 15 dòng `TC-01..TC-15`, không thiếu trường bắt buộc |
| R3-04 | Ít nhất 3 edge cases AI không tìm ra | Full AI output, ảnh hội thoại, 3 edge cases và giải thích | Workbook; `private-evidence/edge-cases/` | NOT STARTED | Đủ `EC-01..EC-03`, chứng minh được output AI ban đầu không chứa chúng |
| R3-05 | Thực thi và quay ít nhất 5 test cases | Video tối đa 60 giây, có giọng nói; Actual và Verdict | `physical-product/video-links.md`; workbook | NOT STARTED | Có ít nhất 5 video xem được và khớp với TC ID |
| R3-06 | Ghi defect của thiết bị vào GitHub Issues | Issue cho mỗi defect thực sự tìm thấy; ảnh trang Issues có username | `physical-product/github-issues.md`; `private-evidence/github/` | NOT STARTED | Mọi defect tìm thấy đều có issue và nội dung khớp kết quả test |
| AI-01 | AI Audit Report theo mẫu 5 phần | Entry cho từng AI-generated batch/artifact | `ai/ai-audit-report.md` | NOT STARTED | Mỗi entry đủ Prompt + Tool, Output, Verdict, Reasoning, Student Fix |
| AI-02 | Thống kê AI accuracy | Số lượng và phần trăm VALID/INVALID/INCOMPLETE | Cuối `ai/ai-audit-report.md` | NOT STARTED | Tổng tỷ lệ bằng 100% và mẫu số là số audit entries |
| AI-03 | AI Critique 200-300 từ | Đoạn critique trong báo cáo | `report/HW01_Report.docx` và PDF | NOT STARTED | Đủ số từ và dựa trên lỗi AI thực tế trong bài |
| AI-04 | Mandatory Disclosure | Đoạn khai báo đúng phần AI làm, sinh viên sửa và tự viết | Báo cáo, trước appendices | NOT STARTED | Không để placeholder; nội dung khớp audit và prompt log |
| AI-05 | AI-02, AI-03, AI-05 templates | AI Audit, Disclosure Form và Privacy Checklist; form cần ký được ký | Báo cáo và `private-evidence/signed-forms/` | NOT STARTED | Đủ đúng template được cung cấp trong thư mục AI Templates của môn |
| LOG-01 | Full prompt log có timestamp | Tool/model, timestamp, full prompt và tham chiếu full output | `ai/prompt-log.md` | NOT STARTED | Mọi prompt thực sự dùng cho bài đều có entry; không có log giả |
| REP-01 | Main report PDF | Requirement 1-3, AI Audit, Critique, Disclosure, Self-assessment | `report/HW01_Report.pdf` | NOT STARTED | Mở được, đủ section và không còn placeholder |
| XLSX-01 | Excel incremental | Test Cases, Checklist, Test Summary Report | `physical-product/HW01_Test_Workbook.xlsx` | NOT STARTED | Có đúng 3 sheet chức năng và dữ liệu nhất quán |
| SUB-01 | ZIP đúng tên và đủ nội dung | File ZIP đã mở kiểm tra | `submission/StudentID_HW01_AI_<grade>.zip` | NOT STARTED | Tên đúng, grade 3 chữ số, đủ nội dung bắt buộc |
| SUB-02 | Nộp Moodle và GitHub repo link | Xác nhận nộp trước deadline | `private-evidence/submission/` | NOT STARTED | Moodle xác nhận nộp và link repo truy cập được |

## 4. Cấu trúc thư mục đề xuất

Chỉ tạo thư mục khi bắt đầu dùng. Không cần tạo file rỗng hoặc bản sao dữ liệu chỉ để làm đầy cấu trúc.

```text
23120205-HW01-QA/
├── README.md
├── HW01_EXECUTION_GUIDE.md
├── 2026.HW01.Jobs.Defects.PhysicalProduct_En.pdf
├── job-market/
│   └── job-postings.md
├── defects/
│   └── software-defects.md
├── physical-product/
│   ├── device-profile.md
│   ├── HW01_Test_Workbook.xlsx
│   ├── video-links.md
│   └── github-issues.md
├── ai/
│   ├── mindmap/
│   │   ├── ai-original.png
│   │   └── corrected-mindmap.md
│   ├── prompt-log.md
│   ├── ai-audit-report.md
│   └── templates/
├── private-evidence/
│   ├── jobs/
│   ├── defects/
│   ├── device/
│   ├── edge-cases/
│   ├── github/
│   ├── signed-forms/
│   └── submission/
├── report/
│   ├── HW01_Report.docx
│   └── HW01_Report.pdf
└── submission/
    └── StudentID_HW01_AI_<grade>.zip
```

### Quy tắc dữ liệu và quyền riêng tư

- `job-market/job-postings.md` là nguồn dữ liệu duy nhất của Requirement 1. Không tạo `job_postings.csv` và không tạo sheet `Job_Postings` trong Excel.
- `private-evidence/` là dữ liệu phục vụ chấm bài, không mặc định là dữ liệu được phép công khai. Nếu repository public, thêm thư mục này vào `.gitignore` trước khi đặt ảnh thật vào đó.
- Chỉ ghi serial đã che trong Markdown, Excel, báo cáo và GitHub Issues. Ví dụ serial gốc `AB123456CD` có thể hiển thị thành `AB12****CD`.
- Không đưa password, email riêng tư, access token, cookie hoặc thông tin thanh toán vào prompt, ảnh hay repository.
- Trước khi push, dùng `git status --short` và danh sách staging để kiểm tra không có file riêng tư bị đưa lên nhầm.

## 5. Quy trình thực hiện chi tiết

## Phase 1 - Khởi tạo và kiểm tra điều kiện

### Bước 1.1 - Khóa thông tin nộp bài

- [ ] Mở Moodle và xác nhận deadline là `13:00 28/09/2026`.
- [ ] Ghi chính xác StudentID sẽ dùng trong tên ZIP và báo cáo.
- [ ] Xác nhận nơi Moodle yêu cầu upload report/ZIP và nơi nhập GitHub repo link.
- [ ] Chụp màn hình deadline và lưu ở `private-evidence/submission/moodle-deadline.png`.

Ảnh deadline cần thấy: tên bài, ngày, giờ và múi giờ hoặc bối cảnh đủ để hiểu đây là deadline của HW01.

### Bước 1.2 - Lấy đúng AI Templates

- [ ] Tải `[AI-02] AI Audit Report` từ thư mục AI Templates của môn.
- [ ] Tải `[AI-03] AI Disclosure Form`.
- [ ] Tải `[AI-05] Privacy & Responsible Use Checklist`.
- [ ] Xác nhận `[AI-06] Student Acknowledgement` đã được ký theo yêu cầu Week 1.
- [ ] Không tự dựng lại template nếu file chính thức đang có trên Moodle/course folder.

### Bước 1.3 - Khóa quy tắc ID

Sử dụng các ID sau trong toàn bộ Markdown, Excel, báo cáo, video và GitHub Issues:

- Job: `JOB-01` đến `JOB-10`.
- Software defect: `DEF-01` đến `DEF-20`.
- Test case: `TC-01` đến `TC-15`.
- Edge case AI bỏ sót: `EC-01` đến ít nhất `EC-03`.
- Video: `VID-01` đến ít nhất `VID-05`.
- Physical-device defect: `PDEF-01`, `PDEF-02`, ... chỉ tạo khi thực sự quan sát thấy defect.

### Gate Phase 1

Phase 1 chỉ `PASS` khi deadline, StudentID, các template bắt buộc và quy tắc ID đã được xác nhận. Nếu chưa tìm được AI Templates chính thức, dừng phần ký/đính kèm form và lấy file từ Moodle/giảng viên; không thay bằng template tự chế.

## Phase 2 - G9.1: QA/QC role mindmap trong ISTQB process

### Bước 2.1 - Tạo output AI gốc

1. Soạn một prompt yêu cầu AI tạo mindmap về vai trò và hoạt động QA/QC trong testing process theo ISTQB.
2. Thực sự gửi prompt cho AI.
3. Ngay sau khi nhận kết quả, ghi vào `ai/prompt-log.md`:
   - timestamp thật theo `HH:MM dd/mm/yyyy`;
   - tên tool và model nếu nhìn thấy;
   - full prompt;
   - full output hoặc đường dẫn đến full output.
4. Lưu output gốc dưới dạng `ai/mindmap/ai-original.png` hoặc Markdown nếu tool chỉ xuất text.

Không chỉnh sửa output AI gốc trước khi lưu. Nếu cần khoanh lỗi, tạo một bản ảnh chú thích riêng; không ghi đè bản gốc.

### Bước 2.2 - Tìm đúng 3 lỗi

Đối chiếu mindmap với ISTQB Foundation Level Syllabus mới nhất được môn sử dụng và course slides. Mỗi lỗi phải có đủ:

| Trường | Nội dung cần ghi |
|---|---|
| Mistake ID | `MM-ERR-01`, `MM-ERR-02`, `MM-ERR-03` |
| AI claim | Nguyên văn nút/câu AI viết sai |
| Loại lỗi | Sai khái niệm, sai quan hệ, thiếu trách nhiệm, nhầm QA/QC, hoặc diễn đạt gây hiểu sai |
| Evidence | Tên slide hoặc section ISTQB dùng để đối chiếu |
| Vì sao sai | Giải thích ngắn, cụ thể |
| Student fix | Nội dung thay thế chính xác |

Không dùng ba cách diễn đạt khác nhau của cùng một lỗi để tính thành ba lỗi.

### Bước 2.3 - Tạo bản sửa và audit entry

- [ ] Tạo `ai/mindmap/corrected-mindmap.md`.
- [ ] Đánh dấu rõ nội dung nào đã thay đổi so với AI output.
- [ ] Tạo một AI Audit entry cho toàn bộ mindmap nếu nó được sinh từ một prompt.
- [ ] Verdict phải phản ánh toàn bộ batch: `VALID`, `INVALID` hoặc `INCOMPLETE` và có lý do.

### Gate Phase 2

- Có output nguyên bản.
- Có prompt và timestamp thật.
- Có đúng 3 lỗi độc lập.
- Mỗi lỗi có căn cứ ISTQB/course material.
- Có bản sửa và AI Audit entry.

## Phase 3 - Requirement 1: 10 QA/QC job postings

### Bước 3.1 - Sàng lọc ứng viên

Với từng job, kiểm tra theo thứ tự:

1. Chức danh và mô tả thực sự thuộc QA/QC, software testing, quality engineering hoặc test automation.
2. Ngày đăng nằm trong cửa sổ hợp lệ.
3. Trang còn truy cập được và có đủ JD/skills.
4. Có thể mở trong trạng thái đăng nhập để chụp display name.
5. Nếu dùng cho quota AI, JD phải có câu yêu cầu hoặc trách nhiệm liên quan AI, LLM hoặc AI-assisted automation rõ ràng.

Không tính một job là AI-related chỉ vì công ty làm AI hoặc chức danh có từ “automation”. Test automation thông thường không tự động đồng nghĩa với automation-AI.

### Bước 3.2 - Chụp bằng chứng

Mỗi `JOB-*` nên có một ảnh dài hoặc nhiều ảnh được đặt tên cùng ID, ví dụ:

```text
private-evidence/jobs/JOB-01-overview.png
private-evidence/jobs/JOB-01-details.png
```

Tổng bằng chứng của mỗi job phải nhìn thấy:

- [ ] Job title.
- [ ] Company.
- [ ] Ngày đăng cụ thể.
- [ ] Display name/tên tài khoản ở góc giao diện job platform.
- [ ] Phần JD và required skills dùng trong record.
- [ ] Câu yêu cầu AI nếu job được tính vào quota AI.
- [ ] Salary nếu trang có công bố.

Nếu một màn hình không chứa đủ tất cả thông tin, chụp thêm ảnh cùng ID. Không ghép nội dung từ hai job khác nhau vào một record.

### Bước 3.3 - Ghi `job-postings.md`

Dùng mẫu sau cho mỗi job:

```markdown
## JOB-01 - <Job title>

- Company:
- Location:
- Posting date:
- Capture date:
- Source URL:
- Salary: <giá trị công bố hoặc Not disclosed>
- AI-related: Yes/No
- AI evidence: <trích ngắn câu yêu cầu AI hoặc N/A>
- Evidence files:
  - `private-evidence/jobs/JOB-01-overview.png`
  - `private-evidence/jobs/JOB-01-details.png`

### Job description
<Tóm tắt trung thực các nhiệm vụ chính>

### Required skills
- <Skill 1>
- <Skill 2>

### AI Impact Analysis
<1-2 câu phân tích AI có thể thay thế, hỗ trợ hoặc chưa thể thay thế phần việc nào của vị trí này và vì sao.>
```

Quy tắc salary:

- Có con số trên nguồn: ghi đúng con số, currency và chu kỳ (`per year`, `per hour`, ...).
- Không công bố: ghi `Not disclosed`.
- Không đổi currency, nội suy hoặc lấy salary trung bình bên ngoài để điền thay.

### Bước 3.4 - Kiểm tra chéo Requirement 1

- [ ] Có đúng 10 heading từ `JOB-01` đến `JOB-10`.
- [ ] Có đúng 10 source URLs.
- [ ] Có 10 posting dates hợp lệ.
- [ ] Có 10 AI Impact Analyses.
- [ ] Có ít nhất 3 dòng `AI-related: Yes` với câu chứng minh nhìn thấy trong JD/ảnh.
- [ ] Có ảnh đăng nhập cho cả 10 job.

### Gate Phase 3

Chỉ `PASS` khi 10/10 record hoàn chỉnh, 10/10 bộ ảnh có display name và ít nhất 3 job có bằng chứng yêu cầu AI rõ ràng. Danh sách link chưa có ảnh không phải bằng chứng hoàn chỉnh.

## Phase 4 - Requirement 2: 20 software defects 2022-2026

### Bước 4.1 - Chọn defect và nguồn

- Chọn 20 sự cố/lỗi phần mềm được publicized từ ngày 01/01/2022 đến hết năm 2026 tính đến thời điểm làm bài.
- Dùng nguồn có thể kiểm chứng: vendor advisory, CVE/NVD, incident report, engineering post, cơ quan quản lý hoặc báo chí uy tín.
- Ít nhất 5 defect phải thực sự liên quan AI/LLM, ví dụ hallucination, prompt injection, bias hoặc lỗi hệ thống AI.
- Không dùng 20 bài báo nói về cùng một defect như 20 defect khác nhau.

### Bước 4.2 - Ghi record defect

Dùng mẫu sau trong `defects/software-defects.md`:

```markdown
## DEF-01 - <Tên defect/sự cố>

- Publicized date/year:
- Product/system:
- AI-related: Yes/No
- Source URL:
- Additional verification URL: <nếu cần>
- Severity: <mức độ và căn cứ đánh giá>

### Description
<Lỗi là gì và điều kiện xảy ra>

### Consequences
<Ảnh hưởng thực tế hoặc rủi ro>

### Solution/Mitigation
<Cách vendor sửa hoặc biện pháp giảm thiểu có nguồn>

### AI bias/hallucination observation
- Audit entry:
- Exact AI claim:
- Why it is biased/unsupported/false:
- Evidence used to verify:
- Student correction:
```

Severity phải nhất quán. Nếu nguồn có CVSS/severity chính thức, dùng mức đó và dẫn nguồn. Nếu tự đánh giá, ghi rõ `Student assessment` và giải thích tác động; không trình bày như severity chính thức của vendor.

### Bước 4.3 - Kiểm tra AI cho từng defect

1. Hỏi AI giải thích defect theo từng record hoặc batch nhỏ có thể audit được.
2. Giữ full output, không chỉ giữ câu sai.
3. Đối chiếu từng claim quan trọng với nguồn.
4. Chọn một điểm cụ thể AI thể hiện bias hoặc hallucination: bịa nguyên nhân, bịa con số, gán sai vendor, khẳng định quá mức, suy diễn động cơ, hoặc dùng ngôn ngữ thiên lệch không có căn cứ.
5. Trích chính xác câu/ý đó, giải thích vì sao sai và viết correction.

Lưu ý: “AI viết chưa đủ chi tiết” tự nó có thể chỉ là incomplete, chưa chắc đáp ứng yêu cầu bias/hallucination. Ưu tiên một claim sai, không có nguồn hoặc thiên lệch có thể chứng minh. Không tự bịa lỗi AI; nếu output hiện tại hoàn toàn đúng, hỏi AI bằng một prompt phân tích khác hoặc chọn khía cạnh có thể kiểm tra, rồi đánh giá trung thực.

### Bước 4.4 - Kiểm tra chéo Requirement 2

- [ ] Có đủ `DEF-01..DEF-20`.
- [ ] Cả 20 defect có năm trong khoảng yêu cầu.
- [ ] Cả 20 defect có source URL, description, severity, consequences và solution.
- [ ] Ít nhất 5 record có `AI-related: Yes` và nguồn chứng minh.
- [ ] Đủ 20/20 phần AI bias/hallucination observation.
- [ ] Mỗi observation trỏ được đến full AI output/audit entry tương ứng.

### Gate Phase 4

Phase 4 chỉ `PASS` khi 20 record độc lập đều đầy đủ, quota AI đạt tối thiểu 5 và mỗi defect có một nhận xét AI có thể kiểm chứng.

## Phase 5 - Requirement 3: thiết bị vật lý và 15 test cases

### Bước 5.1 - Chọn một thiết bị cụ thể

Chọn thiết bị gia dụng thật mà sinh viên đang sở hữu và có thể thao tác an toàn, ví dụ quạt, nồi cơm điện, máy lọc nước hoặc smart bulb. Không chọn một ứng dụng thuần phần mềm.

Ghi vào `physical-product/device-profile.md`:

```markdown
# Device Profile

- Product type:
- Brand:
- Model:
- Year:
- Masked serial number:
- Main functions in test scope:
- Safety constraints:
- Device photo: `private-evidence/device/DEVICE-ID.jpg`
```

Chỉ che đúng bốn ký tự ở giữa serial. Phần còn lại phải đủ để cho thấy sinh viên đang mô tả một thiết bị cụ thể.

### Bước 5.2 - Chụp ảnh sở hữu thiết bị

Người dùng tự chụp một ảnh duy nhất có:

- [ ] Toàn bộ hoặc phần nhận diện rõ thiết bị.
- [ ] Thẻ sinh viên trong cùng khung hình.
- [ ] Hình ảnh đủ sáng và đọc được thông tin cần đối chiếu.

Không nhờ AI tạo, thay nền hoặc ghép thẻ vào ảnh. Trước khi đưa vào report/ZIP, kiểm tra mức độ lộ thông tin cá nhân; không đưa ảnh này lên repo public.

### Bước 5.3 - Tạo workbook incremental

Tạo một file duy nhất `physical-product/HW01_Test_Workbook.xlsx` với ba sheet:

1. `Test_Cases`
2. `Checklist`
3. `Test_Summary`

Sheet `Test_Cases` tối thiểu có các cột:

| Cột | Nội dung |
|---|---|
| Test Case ID | `TC-01..TC-15` |
| Title | Tên ngắn gọn, phân biệt được mục tiêu |
| Objective | Điều cần xác minh |
| Preconditions | Trạng thái thiết bị trước test |
| Input | Dữ liệu/thao tác đầu vào |
| Steps | Các bước có thứ tự, thực thi được |
| Expected Result | Kết quả mong đợi có thể quan sát |
| Actual Result | Điền sau khi thực thi; chưa chạy ghi `Not Executed` |
| Verdict | `PASS`, `FAIL`, `BLOCKED` hoặc `NOT EXECUTED` |
| Edge Case ID | `EC-*` nếu là edge case AI bỏ sót, nếu không để trống |
| Video ID | `VID-*` nếu có video |
| Issue ID/URL | `PDEF-*` và GitHub Issue URL nếu phát hiện defect |

Các cột Preconditions, Title và liên kết ID giúp thực thi/đối chiếu, nhưng sáu trường đề bắt buộc `Objective / Input / Steps / Expected / Actual / Verdict` phải luôn hiện diện.

Sheet `Checklist` dùng để đánh dấu 15 test case đã được review, test nào được chọn quay video, edge case nào do sinh viên bổ sung và bằng chứng đã đủ hay chưa.

Sheet `Test_Summary` tổng hợp ít nhất:

- Total = 15.
- Executed.
- PASS.
- FAIL.
- BLOCKED.
- NOT EXECUTED.
- Number of recorded videos.
- Number of physical-device defects found.

Các tổng phải khớp dữ liệu trong `Test_Cases`; không nhập số đẹp hơn kết quả thật.

### Bước 5.4 - Chứng minh 3 edge cases AI bỏ sót

1. Dùng một prompt thực tế yêu cầu AI đề xuất test cases cho đúng brand/model/chức năng trong scope; không gửi serial đầy đủ hoặc dữ liệu nhạy cảm.
2. Lưu full prompt và full output.
3. Tự phân tích điều kiện biên hoặc ngữ cảnh sử dụng mà output AI không đề cập.
4. Tạo ít nhất `EC-01..EC-03` và liên kết chúng đến các `TC-*` trong workbook.
5. Với mỗi edge case, ghi:

```markdown
### EC-01 - <Tên edge case>

- Related test case:
- What AI generated:
- Evidence that this case was absent:
- Why AI likely missed it:
- Why the case matters for this exact device:
- Student-designed steps and expected result:
```

6. Chụp phần hội thoại đủ rộng để nhận diện prompt và output. Vì một ảnh nhỏ khó chứng minh một nội dung “không xuất hiện”, phải giữ cả full output trong prompt log/audit report; screenshot là bằng chứng bổ sung có annotation.

### Bước 5.5 - Review 15 test cases trước thực thi

- [ ] Mỗi test case chỉ có một mục tiêu chính.
- [ ] Steps đủ chi tiết để lặp lại.
- [ ] Expected Result có thể quan sát, không dùng câu mơ hồ như “works correctly”.
- [ ] Test data/input phù hợp thiết bị thật.
- [ ] Không có bước nguy hiểm, làm hỏng thiết bị hoặc vi phạm hướng dẫn nhà sản xuất.
- [ ] Đúng 15 test cases, không tính sub-step thành test case riêng để đủ số lượng.
- [ ] Đã chọn ít nhất 5 test cases có thể quay video trong 60 giây.

### Gate Phase 5

Có device profile, ảnh sở hữu hợp lệ, workbook đúng ba sheet, đúng 15 test cases và ít nhất 3 edge cases do sinh viên tự tìm với bằng chứng AI bỏ sót.

## Phase 6 - Thực thi, video và GitHub Issues

### Bước 6.1 - Chuẩn bị thực thi an toàn

- Đọc cảnh báo an toàn/hướng dẫn thiết bị trước khi test.
- Chuẩn bị trạng thái ban đầu và input cho từng test.
- Kiểm tra camera, âm thanh và không gian riêng tư.
- Không quay rõ serial đầy đủ, địa chỉ nhà, credential Wi-Fi hoặc dữ liệu không liên quan.

### Bước 6.2 - Thực thi và cập nhật workbook

Với mỗi test được chạy:

1. Ghi thời điểm thực thi nếu workbook có trường này.
2. Làm đúng Steps đã thiết kế.
3. Ghi Actual Result theo điều quan sát được.
4. So sánh với Expected Result và gán Verdict.
5. Nếu FAIL, tạo `PDEF-*` và chuẩn bị GitHub Issue.
6. Cập nhật `Test_Summary` sau mỗi đợt thực thi.

Không đổi Expected Result sau khi thấy Actual Result chỉ để biến FAIL thành PASS. Nếu test case ban đầu sai, giữ lịch sử thay đổi và giải thích correction.

### Bước 6.3 - Quay ít nhất 5 video

Mỗi video phải tối đa 60 giây và có giọng nói của sinh viên. Kịch bản tối giản:

1. Nói `TC ID` và mục tiêu.
2. Cho thấy trạng thái ban đầu/input.
3. Thực hiện các bước chính.
4. Cho thấy Actual Result.
5. Nói Verdict và lý do.

Đặt ID `VID-01..VID-05+`, sau đó ghi vào `physical-product/video-links.md`:

```markdown
| Video ID | Test Case ID | Platform | Unlisted URL | Duration | Voice | Result |
|---|---|---|---|---:|---|---|
| VID-01 | TC-01 | YouTube | <URL> | 00:45 | Yes | PASS/FAIL |
```

Mở từng link trong cửa sổ không đăng nhập/incognito để kiểm tra giảng viên có thể xem. YouTube Unlisted là nền tảng chính. Chỉ dùng Google Drive/OneDrive nếu YouTube gỡ/chặn do copyright; khi đó lưu bằng chứng bị chặn và cấp đúng quyền xem.

### Bước 6.4 - Ghi physical-device defects vào GitHub Issues

HW01 **không còn dùng FIT Mantis**. Tất cả defect tìm thấy khi test thiết bị vật lý phải được ghi thành Issues trong GitHub repository của chính sinh viên.

Với mỗi defect thực sự tìm thấy, tạo một GitHub Issue có:

```markdown
Title: [PDEF-01][TC-xx] <Tóm tắt defect>

## Environment
- Device:
- Model:
- Year:
- Masked serial:

## Preconditions

## Steps to reproduce
1.
2.

## Expected result

## Actual result

## Severity and rationale

## Evidence
- Video ID/URL:
- Screenshot/photo:
```

- Chụp trang Issues có thể nhìn thấy GitHub username và danh sách issue.
- Ghi mapping `PDEF ID -> TC ID -> GitHub Issue URL` trong `physical-product/github-issues.md`.
- Mục tiêu đề bài là cố gắng tìm ít nhất 5 defect. Nếu không tìm thấy đủ 5 sau khi test trung thực, không tạo issue giả; mở rộng các test case hợp lệ và báo cáo đúng số lượng quan sát được.

### Gate Phase 6

- Có ít nhất 5 test cases được thực thi và 5 video hợp lệ.
- Actual/Verdict trong workbook khớp video.
- Mọi defect thực sự tìm thấy đều có GitHub Issue.
- Có ảnh Issues page nhìn thấy GitHub username.
- Test Summary khớp số liệu thực tế.

## Phase 7 - Prompt log và AI Audit Report

### Bước 7.1 - Quy trình ghi prompt thật

Thực hiện quy trình sau mỗi lần dùng AI cho bài:

1. Trước khi gửi, bỏ PII và dữ liệu không cần thiết khỏi prompt.
2. Gửi prompt thật.
3. Ghi ngay timestamp thực tế.
4. Sao chép nguyên văn full prompt.
5. Lưu full output; không paraphrase thay cho output.
6. Gắn prompt với artifact hoặc audit entry tương ứng.

Mẫu `ai/prompt-log.md`:

```markdown
## PROMPT-01

- Timestamp: HH:MM dd/mm/yyyy
- Tool:
- Model/version shown:
- Purpose:
- Related artifacts: <G9.1 / DEF-* / TC-* / ...>
- Reconstruction status: ORIGINAL

### Full prompt
<Nguyên văn prompt đã thực sự gửi>

### Full output
<Nguyên văn output hoặc đường dẫn tới file/ảnh chứa toàn bộ output>
```

Nếu phải tái dựng thông tin cũ, dùng:

```markdown
- Reconstruction status: RECONSTRUCTED - not an original audit event
- Reconstruction reason: <lý do log gốc không còn>
- Reconstruction timestamp: <thời điểm thực sự tái dựng>
```

Không dùng timestamp ước đoán như thể là timestamp gốc.

### Bước 7.2 - Tạo AI Audit entry theo batch

Một batch được tạo bởi một prompt tính là một artifact/audit entry, kể cả khi output chứa 15 test cases. Mẫu entry:

```markdown
## AUDIT-01 - <Tên artifact/batch>

### 1. Prompt + tool
- Prompt log ID:
- Tool/model:
- Timestamp:
- Full prompt:

### 2. AI output
<Full output hoặc red-bordered screenshot có annotation; không summary/paraphrase>

### 3. Verdict
VALID / INVALID / INCOMPLETE

<Lý do verdict>

### 4. Reasoning
<2-5 câu, dẫn đúng slide hoặc ISTQB section>

### 5. Student fix
<Phiên bản đã sửa; highlight cụ thể phần thay đổi>
```

Nếu dùng screenshot viền đỏ/annotation, vẫn phải bảo đảm người chấm có thể truy cập toàn bộ output, không chỉ phần bị khoanh.

### Bước 7.3 - Tính AI accuracy ratio

Tính trên tổng số audit entries, không tính từng test case trong một batch như một entry riêng.

```text
VALID %     = VALID entries / Total audit entries x 100
INVALID %   = INVALID entries / Total audit entries x 100
INCOMPLETE %= INCOMPLETE entries / Total audit entries x 100
```

Kiểm tra tổng ba tỷ lệ bằng 100%, cho phép sai số làm tròn nhỏ. Cuối báo cáo kết luận rõ khi nào nên và không nên dùng AI cho loại công việc này.

### Bước 7.4 - Đồng bộ log trước commit

Trước mỗi commit có AI-assisted artifact:

- [ ] Mọi prompt mới đã được ghi.
- [ ] Tool/model và timestamp là thật.
- [ ] Full output còn truy cập được.
- [ ] Artifact có audit entry tương ứng.
- [ ] Không có secret hoặc PII trong staged files.

Commit không phải bằng chứng thay thế cho timestamp và full prompt; nó chỉ giúp bảo toàn lịch sử thay đổi.

### Gate Phase 7

Mọi AI-generated artifact đều truy ngược được tới prompt log và audit entry. Không có entry giả, không có output bị tóm tắt thay cho bản đầy đủ, và accuracy ratio được tính đúng.

## Phase 8 - Báo cáo và self-assessment

### Bước 8.1 - Cấu trúc main report

Sắp xếp báo cáo PDF theo cấu trúc sau:

1. Cover page: StudentID, tên bài, ngày nộp.
2. Requirement 1 - QA/QC Job Market 2026+.
3. Requirement 2 - 20 Software Defects 2022-2026.
4. Requirement 3 - Physical Product Test Design and Execution.
5. G9.1 Mindmap Critique and Correction.
6. AI Audit Report.
7. AI Critique.
8. Mandatory Disclosure.
9. Self-Assessment.
10. Appendices/evidence references.

Đề bài yêu cầu AI Audit Report, AI Critique và Mandatory Disclosure nằm trong main report. Không chỉ đặt chúng ở file rời mà bỏ khỏi PDF.

Để xử lý cách gọi tên có thể gây nhầm trong đề: giữ **AI Audit Report** thành một section đầy đủ trong main report; dùng **Appendix A** cho full prompt log theo danh sách nội dung ZIP. Trong Mandatory Disclosure, giữ nguyên câu chuẩn của template chính thức thay vì tự sửa wording. Như vậy cả AI Audit Report và prompt log đều hiện diện, dù cách đánh nhãn appendix trong các đoạn của đề không hoàn toàn đồng nhất.

### Bước 8.2 - Viết AI Critique 200-300 từ

Đoạn critique phải trả lời:

- AI sai, biased hoặc incomplete ở đâu?
- Vì sao AI không bắt được vấn đề?
- Sinh viên đã kiểm tra/sửa bằng nguyên tắc hoặc nguồn nào?
- Bài học về việc khi nào nên và không nên cộng tác với AI trong HW này là gì?

Chỉ dùng ví dụ thực tế đã xuất hiện trong mindmap, defect analysis hoặc test-case generation. Đếm từ trước khi xuất PDF và giữ trong khoảng 200-300 từ theo ngôn ngữ báo cáo.

### Bước 8.3 - Mandatory Disclosure

Dùng đúng template chuẩn trong đề và thay toàn bộ placeholder bằng thông tin thật:

> “[Test cases / script / dataset / report] was initially generated by [AI tool name]; I reviewed and modified [section X], added [edge cases Y, Z]; [section W] was written entirely by me. The detailed AI Audit Report is attached as Appendix A. I confirm I did not use AI to generate any artifact listed in the prohibited category below.”

Nội dung khai báo phải khớp prompt log, audit entries và lịch sử artifact. Không khai báo “written entirely by me” cho phần thực tế đã được AI sinh hoặc sửa nội dung.

### Bước 8.4 - Self-assessment

Tự chấm theo đúng rubric:

| Tiêu chí | Điểm tối đa | Chỉ tự nhận khi |
|---|---:|---|
| Job Market 2026+ | 40 | Đủ 10 job, bằng chứng và AI Impact |
| Software Defects 2022-2026 | 20 | Đủ 20 defect và yêu cầu AI observation |
| Physical-product test design | 25 | Đủ 15 test cases, execution và ít nhất 5 video |
| AI-1: AI Audit Report | 8 | Audit 5 phần đầy đủ |
| AI-2: Critique + Disclosure | 4 | Critique 200-300 từ và AI-03 hợp lệ |
| AI-3: Privacy + anti-cheat | 3 | AI-05 ký và bằng chứng cá nhân hợp lệ |
| **Total** | **100** | Tổng bằng chứng đã kiểm tra |

Grade dùng trong tên ZIP phải là số có ba chữ số từ `000` đến `100`, ví dụ `085`, không phải `85`.

### Bước 8.5 - Review report trước xuất PDF

- [ ] Tất cả heading bắt buộc tồn tại.
- [ ] Không còn placeholder dạng `<...>`, `[section X]` hoặc nội dung mẫu chưa thay.
- [ ] Bảng và ảnh đọc được, có caption/ID.
- [ ] Link bấm được hoặc URL được ghi đầy đủ.
- [ ] Serial luôn được che đúng quy tắc.
- [ ] AI Critique đủ 200-300 từ.
- [ ] Disclosure, prompt log và audit report không mâu thuẫn.
- [ ] Self-assessment cộng đúng 100 điểm tối đa.

### Gate Phase 8

`report/HW01_Report.pdf` mở được, đủ section, số liệu khớp source artifacts và không còn placeholder hoặc dữ liệu riêng tư ngoài chủ ý.

## Phase 9 - Đóng gói, kiểm tra và nộp

### Bước 9.1 - Tạo ZIP

Tên bắt buộc:

```text
StudentID_HW01_AI_<grade>.zip
```

Checklist nội dung ZIP:

- [ ] Main report PDF có AI Audit Report, AI Critique và Mandatory Disclosure.
- [ ] Appendix A: full prompt log `.md` hoặc `.txt` có timestamp.
- [ ] `HW01_Test_Workbook.xlsx` với Test Cases, Checklist và Test Summary.
- [ ] Device photo + student-ID card `.jpg`.
- [ ] Danh sách YouTube Unlisted links của ít nhất 5 video.
- [ ] QA/QC role mindmap bản gốc và bản sửa phù hợp.
- [ ] `[AI-02]` AI Audit Report.
- [ ] `[AI-03]` AI Disclosure Form đã ký nếu template yêu cầu ký.
- [ ] `[AI-05]` Privacy Checklist đã ký.
- [ ] Các bằng chứng khác được report tham chiếu nhưng không truy cập được từ bên ngoài ZIP.

### Bước 9.2 - Kiểm tra ZIP như người chấm

1. Giải nén vào một thư mục tạm khác với workspace.
2. Mở report PDF từ bản giải nén.
3. Mở Excel và kiểm tra ba sheet.
4. Mở ảnh thiết bị.
5. Mở prompt log và tìm một prompt bất kỳ từ report.
6. Mở toàn bộ video links trong trạng thái không đăng nhập.
7. Kiểm tra file ký đọc được.
8. Kiểm tra không có file tạm, secret, ảnh dư hoặc bản nháp gây nhầm lẫn.

### Bước 9.3 - Kiểm tra GitHub repository

- [ ] Repository link truy cập được theo quyền dự kiến.
- [ ] Các artifact được phép chia sẻ đã được push.
- [ ] Mọi physical-device defect tìm thấy có GitHub Issue.
- [ ] Ảnh Issues page có GitHub username đã được đưa vào bộ bằng chứng nộp.
- [ ] Không có ảnh thẻ sinh viên, signed forms, serial đầy đủ, credentials hoặc private evidence trong repo public.
- [ ] `git status --short` không còn thay đổi ngoài ý muốn.

### Bước 9.4 - Nộp Moodle

- [ ] Upload đúng report/ZIP theo form Moodle.
- [ ] Dán đúng GitHub repo link.
- [ ] Kiểm tra filename và self-assessed grade lần cuối.
- [ ] Submit trước `13:00 28/09/2026`.
- [ ] Chụp trang xác nhận nộp có timestamp và lưu vào `private-evidence/submission/`.

### Gate Phase 9

ZIP mở được, mọi link truy cập được, GitHub không lộ dữ liệu cấm và Moodle hiển thị trạng thái nộp thành công trước deadline.

## 6. Checklist kiểm tra cuối cùng theo số lượng

| Hạng mục | Mục tiêu | Thực tế | PASS/FAIL |
|---|---:|---:|---|
| Job postings | 10 |  |  |
| Job screenshots có display name | 10 |  |  |
| AI-related jobs có bằng chứng rõ | >= 3 |  |  |
| AI Impact Analyses | 10 |  |  |
| Software defects | 20 |  |  |
| AI/LLM-related defects | >= 5 |  |  |
| Defects có AI bias/hallucination observation | 20 |  |  |
| Mindmap mistakes được sửa | 3 |  |  |
| Physical products | 1 |  |  |
| Test cases | 15 |  |  |
| AI-missed edge cases | >= 3 |  |  |
| Executed test cases có video | >= 5 |  |  |
| Video có giọng nói và <= 60 giây | >= 5 |  |  |
| GitHub Issues | Bằng số defect thiết bị thực sự tìm thấy |  |  |
| AI Critique | 200-300 từ |  |  |
| AI Audit entries đủ 5 phần | 100% AI artifacts |  |  |
| Prompt log có timestamp thật | 100% prompts |  |  |
| AI-02 / AI-03 / AI-05 | Đủ 3 |  |  |
| AI-06 | Đã ký theo quy định |  |  |
| Main report PDF | 1 |  |  |
| Excel workbook | 1, đủ 3 sheet |  |  |
| Submission ZIP | 1 |  |  |

Nếu bất kỳ dòng bắt buộc nào `FAIL`, chưa đóng gói bản cuối.

## 7. Kiểm tra consistency giữa các artifact

Thực hiện kiểm tra chéo trước khi nộp:

1. Mỗi `JOB-*` trong report phải tồn tại trong `job-postings.md` và trỏ đúng ảnh.
2. Mỗi `DEF-*` trong report phải tồn tại trong `software-defects.md` và AI Audit entry tương ứng.
3. Mỗi `EC-*` phải trỏ đến một `TC-*`, full AI output và phần giải thích.
4. Mỗi `VID-*` phải trỏ đến đúng `TC-*`; video result phải khớp Actual/Verdict.
5. Mỗi `PDEF-*` phải trỏ đến test case phát hiện nó và GitHub Issue URL.
6. Tổng PASS/FAIL/BLOCKED/NOT EXECUTED trong Test Summary phải bằng 15.
7. Số AI Audit entries dùng trong accuracy ratio phải bằng số entry thực có.
8. Mandatory Disclosure phải khớp prompt log và audit report.
9. Self-assessed grade trong report phải khớp ba chữ số trong tên ZIP.
10. Mọi đường dẫn tương đối trong Markdown phải trỏ đến đúng file dự kiến.

## 8. Kiểm tra Git trước khi commit/push

Chạy và đọc kết quả từng lệnh:

```bash
git status --short
git add --dry-run .
git diff --check
```

Nếu đã stage file, kiểm tra thêm:

```bash
git diff --cached --stat
git diff --cached --check
```

Trước khi commit, xác nhận danh sách không chứa:

- `private-evidence/` nếu repo public.
- Ảnh thẻ sinh viên.
- Signed forms.
- Serial chưa che.
- Credential/token/cookie.
- File ZIP nộp Moodle chứa dữ liệu riêng tư, trừ khi repo là private và việc lưu ZIP đã được cân nhắc rõ ràng.

Không dùng `git add .` một cách máy móc trước khi xem `git add --dry-run .`.

## 9. Định nghĩa hoàn thành HW01

Chỉ coi bài hoàn thành khi đồng thời đạt tất cả điều kiện:

- Các Phase 1-9 đều qua gate.
- Bảng số lượng cuối không có dòng bắt buộc bị thiếu.
- Report, Excel, ảnh, form và ZIP đều mở được.
- Ít nhất 5 video xem được bằng quyền của người chấm.
- GitHub Issues và repo link truy cập được.
- Prompt log và AI disclosure trung thực, thống nhất.
- Không có dữ liệu riêng tư bị publish ngoài chủ ý.
- Moodle xác nhận nộp thành công trước deadline.

Nếu chỉ có link nghiên cứu, draft test case hoặc checklist chưa có bằng chứng cá nhân, phần tương ứng vẫn là `IN PROGRESS`, không phải `PASS`.
