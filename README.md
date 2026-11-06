# Notebook Xác suất Thống kê

Đây là sổ tay học môn **Xác suất Thống kê (XSTK)**. Thư mục gồm tài liệu gốc của môn, bài giảng chép lại bằng LaTeX và bài tập nộp theo từng chương.

## Cấu trúc thư mục

```
.
├── TaiLieu/                  # Tài liệu gốc (PDF, DOCX, PPTX), không chỉnh sửa
│   ├── Phần 1. Xác suất _ file pdf/   # Chương 1–5: lý thuyết + bài tập
│   ├── Phần 2. Thống kê/              # Lý thuyết mẫu, ước lượng, kiểm định, hồi quy
│   ├── Bảng Phân Phối.pdf
│   ├── NỘI DUNG XSTK.docx
│   └── ...                            # Giáo trình tham khảo
├── TaiLieu.tex/              # Bài giảng chép lại bằng LaTeX
│   └── XacSuat/
│       └── Chuong1/
│           ├── Chuong1.tex        # Bài giảng Chương 1 (bản đầy đủ, biên dịch độc lập)
│           ├── main.tex           # Bản chia file: preamble + \input{Chuong1_body.tex}
│           └── Chuong1_body.tex   # Phần nội dung dùng cho main.tex
└── BaiTapNop/                # Bài tập nộp
    ├── BaiTapChuong1/
    │   └── BaiTapChuong1.tex  # Lời giải 11 bài tập Chương 1
    └── BaiTapChuong2/
```

## Biên dịch

Cần cài TeX Live (hoặc MiKTeX) có gói `vietnam` (`texlive-lang-other` trên Debian/Ubuntu).

```bash
cd BaiTapNop/BaiTapChuong1
pdflatex BaiTapChuong1.tex
pdflatex BaiTapChuong1.tex   # chạy lần 2 để cập nhật tham chiếu
```

Có thể dùng `latexmk -pdf BaiTapChuong1.tex` thay cho hai lệnh trên. Các file trung gian (`.aux`, `.log`, `.out`, ...) đã được loại trong `.gitignore`.

## Quy ước

- Mỗi chương có một bài giảng `TaiLieu.tex/XacSuat/ChuongN/ChuongN.tex` và một bài nộp `BaiTapNop/BaiTapChuongN/BaiTapChuongN.tex`.
- Lời giải bài tập phải dùng ký hiệu và phương pháp đã có trong bài giảng của chương đó, ví dụ $C_n^k$, $P(A|B)$, hệ đầy đủ, công thức Bayes, $P_n(k,p)$.
- File LaTeX dùng `\usepackage[utf8]{vietnam}` với font Times (`mathptmx`), khổ A4. Số thập phân viết theo kiểu Việt Nam: `0{,}5`.

## Tiến độ

| Chương | Nội dung | Bài giảng `.tex` | Bài tập nộp |
|---|---|---|---|
| 1 | Xác suất của biến cố | Có | Có (11 bài) |
| 2 | Biến ngẫu nhiên | Chưa | Chưa |
| 3 | Luật phân phối | Chưa | Chưa |
| 4 | Công thức xấp xỉ | Chưa | Chưa |
| 5 | Vector ngẫu nhiên (tham khảo) | Chưa | Chưa |
