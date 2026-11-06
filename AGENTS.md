# AGENTS.md

Hướng dẫn cho AI agent (Claude Code, Codex, ...) khi làm việc trong project này.

## Project là gì

Sổ tay học môn Xác suất Thống kê bằng tiếng Việt. Thư mục gồm tài liệu gốc, bài giảng chép lại bằng LaTeX và lời giải bài tập nộp theo chương. Đây không phải dự án phần mềm: không có code, không có test, không có build system ngoài LaTeX.

## Thư mục

| Đường dẫn | Vai trò | Được sửa? |
|---|---|---|
| `TaiLieu/` | Tài liệu gốc của giảng viên (PDF/DOCX/PPTX) | **Không**. Chỉ đọc |
| `TaiLieu.tex/XacSuat/ChuongN/ChuongN.tex` | Bài giảng chương N bằng LaTeX, cuối file có đề bài tập | Chỉ khi được yêu cầu |
| `TaiLieu.tex/XacSuat/ChuongN/main.tex` + `ChuongN_body.tex` | Bản chia file của cùng bài giảng | Giữ đồng bộ với `ChuongN.tex` nếu sửa |
| `BaiTapNop/BaiTapChuongN/BaiTapChuongN.tex` | Bài nộp của chương N | Có |

## Quy tắc khi giải bài tập

1. **Đọc bài giảng của chương trước khi giải.** Đề bài nằm trong mục "Bài tập vận dụng" của `ChuongN.tex`. Nếu file `.tex` chưa có, xem PDF tương ứng trong `TaiLieu/Phần 1. Xác suất _ file pdf/`.
2. **Giải bằng phương pháp của bài giảng**, không dùng công cụ của chương sau. Ví dụ Chương 1 chỉ dùng xác suất cổ điển, hình học, công thức cộng, công thức nhân, xác suất có điều kiện, xác suất đầy đủ, Bayes và Bernoulli. Chưa dùng biến ngẫu nhiên hay kỳ vọng.
3. **Giữ ký hiệu như bài giảng:** $C_n^k$ (không dùng $\binom{n}{k}$), $P(A|B)$, $\overline{A}$, $AB$ cho tích biến cố, $P_n(k, p)$, "hệ đầy đủ".
4. Mỗi câu trình bày theo thứ tự: chép đề, đặt tên biến cố, nêu công thức áp dụng, tính, rồi ghi `\dapso{...}`.
5. **Kiểm tra số liệu** (ví dụ bằng `python3 -c ...`) trước khi ghi kết quả. Lời giải mẫu trong bài giảng có thể sai, nên tự đối chiếu.

## Quy ước LaTeX

- Preamble lấy theo `TaiLieu.tex/XacSuat/Chuong1/Chuong1.tex`: `\usepackage[utf8]{vietnam}`, `mathptmx`, `geometry` A4 (trái 2,5cm, phải 2cm), `amsmath/amssymb/amsthm`, `enumitem`, `hyperref`.
- Số thập phân viết dấu phẩy trong math mode: `0{,}95`. Phần trăm viết `95\%`.
- Bài nộp dùng môi trường `cau` (`\newtheorem{cau}{Câu}`), macro `\giai` và `\dapso{}`. Xem `BaiTapNop/BaiTapChuong1/BaiTapChuong1.tex` làm mẫu.

## Biên dịch và kiểm tra

```bash
cd BaiTapNop/BaiTapChuongN
pdflatex -interaction=nonstopmode BaiTapChuongN.tex
pdflatex -interaction=nonstopmode BaiTapChuongN.tex | grep -E "^!|Output written|Overfull"
```

Chỉ báo xong khi lệnh không còn dòng `!` (lỗi). Không commit file trung gian `.aux/.log/.out`, vì chúng đã có trong `.gitignore`.

## Ngôn ngữ

Trả lời người dùng và viết lời giải bằng **tiếng Việt**.
