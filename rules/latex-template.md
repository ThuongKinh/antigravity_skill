# LaTeX Template Rule

Khi tạo file LaTeX mới (`.tex`) cho bài tập, **luôn sử dụng template chuẩn** sau đây trừ khi user yêu cầu khác:

## QUY TẮC CỐT LÕI VỀ BOX ĐỀ (BẮT BUỘC TUÂN THỦ)
- **TUYỆT ĐỐI KHÔNG TỰ Ý VIẾT BOX ĐỀ (`\begin{baitap}...\end{baitap}`)!**
- **KHÔNG chép lại đề bài** vào file LaTeX khi làm bài tập / BTVN.
- Môi trường `baitap`, `dinhly`, `canhbao` chỉ được khai báo trong preamble để phòng trường hợp cần thiết, **tuyệt đối KHÔNG tự ý chèn khối `baitap` vào phần nội dung** trừ khi người dùng yêu cầu đích danh.
- **Định dạng chuẩn:** Chỉ cần 1 dòng ngắn gọn ghi tên bài, câu (ví dụ: `\noindent\textbf{Bài 1.}` hoặc `\textbf{\large Bài 1.}` `\textbf{a)}`), sau đó vào thẳng `\begin{loigiai}...\end{loigiai}`.

---

## Template chuẩn

- Engine: **XeLaTeX**
- Font: **DejaVu Sans**
- Paper: A4, margins 2cm top/left/right, 2.5cm bottom
- Packages bắt buộc: `amsmath, amssymb, amsthm, mathtools, array, booktabs, makecell, enumitem, fancyhdr, tcolorbox[most], xcolor`
- Header: HCMUS – Khoa Toán - Tin học | Tên môn | Ngày
- Footer: Trang số

### Bảng màu "Purple 14 Plus"
- **lilac** (bài tập): bg `#FAF7FD`, border `#9F86C0`, title `#4A3E5C`, shadow `#D1C4E9`
- **rose** (định lý): bg `#FDF8F9`, border `#D49EA7`, title `#663A42`
- **taupe** (cảnh báo): bg `#FAF9F6`, border `#C5BAAF`, title `#54483E`

### Environments có sẵn trong Preamble
- `\begin{baitap}[tên]` — Khối bài tập (chỉ dùng khi user yêu cầu đích danh, KHÔNG tự ý dùng)
- `\begin{dinhly}[tên]` — Khối định lý/tính chất (rose)
- `\begin{canhbao}[tên]` — Khối lưu ý bẫy logic (taupe)
- `\begin{loigiai}...\end{loigiai}` — Lời giải, kết thúc bằng ∎

### Custom commands
- `\then` → `\to`
- `\eqv` → `\leftrightarrow`
- `\R, \N, \Z` → blackboard bold
- `\T` → **Đ** (đúng), `\F` → **S** (sai)
- `\norm{x}` → ‖x‖
- `\rank`, `\Tr` — math operators

### Thông tin sinh viên
- Sinh viên: **Hồ Xuân Phúc**
- Lớp: **26TTH2**

### Template đầy đủ

```latex
\documentclass[11pt,a4paper]{article}

% =========================================================================
% 1. ĐỊNH DẠNG TRANG & FONT TIẾNG VIỆT (XELATEX)
% =========================================================================
\usepackage[top=2cm, bottom=2.5cm, left=2cm, right=2cm]{geometry}
\usepackage{parskip}
\usepackage{fontspec}
\setmainfont{DejaVu Sans}

% =========================================================================
% 2. BỘ CÔNG CỤ TOÁN HỌC & GIẢI THÍCH
% =========================================================================
\usepackage{amsmath, amssymb, amsthm, mathtools}
\usepackage{array, booktabs, makecell}
\usepackage{enumitem}

\newcommand{\then}{\to}
\newcommand{\eqv}{\leftrightarrow}
\newcommand{\R}{\mathbb{R}}
\newcommand{\N}{\mathbb{N}}
\newcommand{\Z}{\mathbb{Z}}
\newcommand{\T}{\textbf{Đ}}
\newcommand{\F}{\textbf{S}}
\newcommand{\norm}[1]{\left\| #1 \right\|}
\DeclareMathOperator{\rank}{rank}
\DeclareMathOperator{\Tr}{tr}

% =========================================================================
% 3. HEADER & FOOTER
% =========================================================================
\usepackage{fancyhdr}
\pagestyle{fancy}
\setlength{\headheight}{13.0pt}
\fancyhf{}
\lhead{\small \textbf{HCMUS} -- Khoa Toán - Tin học}
\chead{\small TÊN MÔN}
\rhead{\small \today}
\rfoot{\small Trang \thepage}
\renewcommand{\headrulewidth}{0.4pt}

% =========================================================================
% 4. KHỐI TRANG TRÍ TCOLORBOX (TÍM PHẤN 14 PLUS + NỔI KHỐI 3D)
% =========================================================================
\usepackage[most]{tcolorbox}
\usepackage{xcolor}

\definecolor{lilacBg}{HTML}{FAF7FD}
\definecolor{lilacBorder}{HTML}{9F86C0}
\definecolor{lilacTitle}{HTML}{4A3E5C}
\definecolor{lilacShadow}{HTML}{D1C4E9}

\definecolor{roseBg}{HTML}{FDF8F9}
\definecolor{roseBorder}{HTML}{D49EA7}
\definecolor{roseTitle}{HTML}{663A42}

\definecolor{taupeBg}{HTML}{FAF9F6}
\definecolor{taupeBorder}{HTML}{C5BAAF}
\definecolor{taupeTitle}{HTML}{54483E}

\newtcolorbox{baitap}[1][]{
	enhanced,
	colback=lilacBg,
	colframe=lilacBorder,
	coltitle=lilacTitle,
	fonttitle=\bfseries\small,
	title={Bài tập: #1},
	arc=2.5mm,
	boxrule=0.75pt,
	fuzzy shadow={1.2mm}{-1.2mm}{0mm}{0.2mm}{lilacShadow!70!black},
	left=11pt, right=11pt, top=7pt, bottom=7pt,
	before skip=12pt, after skip=14pt
}

\newtcolorbox{dinhly}[1][]{
	enhanced,
	colback=roseBg,
	colframe=roseBorder,
	coltitle=roseTitle,
	fonttitle=\bfseries\small,
	title={Định lý / Tính chất: #1},
	arc=2.5mm,
	boxrule=0.75pt,
	fuzzy shadow={1mm}{-1mm}{0mm}{0.2mm}{roseBorder!50!black},
	left=11pt, right=11pt, top=7pt, bottom=7pt,
	before skip=12pt, after skip=14pt
}

\newtcolorbox{canhbao}[1][]{
	enhanced,
	colback=taupeBg,
	colframe=taupeBorder,
	coltitle=taupeTitle,
	fonttitle=\bfseries\small,
	title={Lưu ý bẫy logic: #1},
	arc=2mm,
	boxrule=0.75pt,
	left=10pt, right=10pt, top=7pt, bottom=7pt,
	before skip=10pt, after skip=10pt
}

\newenvironment{loigiai}{%
	\par\noindent\textbf{\textit{Lời giải:}}\par
}{%
	\hfill$\blacksquare$\par
}

% =========================================================================
% 5. BẮT ĐẦU VĂN BẢN
% =========================================================================
\begin{document}

\begin{center}
	{\LARGE \textbf{BÀI TẬP TÊN MÔN -- BUỔI N}}\\[5pt]
	\textbf{Sinh viên: Hồ Xuân Phúc} \quad | \quad \textbf{Lớp: 26TTH2}
\end{center}
\hrule \vspace{10pt}

% ĐỊNH DẠNG CHUẨN: KHÔNG DÙNG BOX ĐỀ \begin{baitap}, VÀO THẲNG BÀI VÀ LỜI GIẢI
\noindent\textbf{Bài 1.}
\begin{loigiai}
% Lời giải trực tiếp ở đây (TUYỆT ĐỐI KHÔNG tự ý viết box đề \begin{baitap})
\end{loigiai}

\end{document}
```
