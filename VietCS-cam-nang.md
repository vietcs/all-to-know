[TOC]

# Quy định chung

## Quy định về hình thức 

- Thời lượng đọc: lý tưởng là từ 5 đến 8 phút.

- Một đoạn văn tối đa 4 câu là phải xuống dòng

- Số hình tối thiểu: mỗi mục nhỏ ít nhất 1 tấm hình.

- Nội dung của các đề mục phải liên kết với nhau.

- Ngôn ngữ: **tiếng Việt**, sử dụng các thuật ngữ tiếng Anh. Tuy nhiên cố gắng dịch trừ khi sử dụng từ tiếng Việt mang cảm giác gượng.

  

## Quy định về chất lượng

- Số người review: ít nhất 3 người review và 50% trở lên đồng ý.

- Một số thứ nên có:
  - Nên viết theo kiểu quy nạp (top-down) sẽ đỡ buồn ngủ hơn
  - Hiệu ứng "Ồ quao": Bài viết nên có yếu tố lạ, bất ngờ
  - Nên đặt các câu hỏi thảo luận: Cái gì, tại sao, khi nào?

- Triết lý khi viết bài: Viết để học, viết để thảo luận, viết để khám phá những "miền đất" mới :))

# Hướng dẫn đăng bài

## Cài đặt

**Bước 0:** Tại và cài đặt [git](https://git-scm.com/downloads)

**Bước 1:** Tải và cài đặt Hugo trên máy

Truy cập github's [releases](https://github.com/gohugoio/hugo/releases) của hugo **v0.58++**. Tải bản **hugo_extended** (phải là bản extended!) phiên bản mới nhất (đuôi .deb hoặc .tar.gz). Sau đó có thể nhấn vào để cài trên GUI **hoặc** có thể cài thông qua terminal:

```bash
TEMP_DEB="$(mktemp)" &&
wget -O "$TEMP_DEB" 'duong-dan-hugo-file.deb' &&
sudo dpkg -i "$TEMP_DEB"
rm -f "$TEMP_DEB"
```



**Bước 2:** clone websource của VietCS về

```bash 
git clone https://github.com/patrickphatnguyen/vietcs-blog.git
cd vietcs-web
git submodule update --init --recursive
```

**Bước 3:** Tải công cụ viết markdown: vscode,... Nhưng khuyến khích nên dùng typora, download [tại đây](https://www.typora.io/) vì đơn giản cho người mới, giao diện đẹp người dùng lâu cũng thấy thoải mái.

## Đăng bài

**Bước 3:** Tạo file markdown và chuẩn bị viết bài!

 ```bash
hugo new <chủ-đề>/<tên-file>.md
 ```

Hiện nay có 1 số chủ đề:

- computer vision "cổ điển" : `cv`
- computer vision "hiện đại" : `mcv`
- công nghệ đóng gói: `tech`
- toán cho CS: `math`

Ví dụ: Bạn viết 1 bài về gioi-thieu-cv về chủ đề Computer Vision 

```bash
hugo new cv/gioi-thieu-cv.md
```

**Bước 4:** Mỗi 1 bài viết có 1 header, điều chỉnh header của file bài viết sao cho phù hợp. Header tiêu chuẩn sẽ trông như thế 

```md
---
title: "Bạn biết gì về Computer Vision?"
date: 2019-10-13T13:34:08+07:00
draft: false
authors: ["phatnt"]
categories:
  - computer vision
tags:
  - introductory
  - vision
slug: computer-vision-la-gi
---
```

Trong đó:

`date` ngày viết

`authors` các tác giả cùng viết bài viết (Nếu bạn chưa có tên viết tắt thì thông báo cho **web owner**)

`categories` chủ đề của bài viết

`tags` đính kèm của bài viết

`slug` link dẫn tới bài viết, có dạng `vietcs/posts/../<slug>`

**Bước 5: **Review xem trước trang web tại local, xem bài của bạn hiện lên trang như thế nào

```bash
hugo serve
```

**Bước 6:** Commit bài lên github

```bash
git add .
git commit -m "Dang bai moi: <ten post>"
git push origin master
```

**Bước 6:** Báo cho **Web Owner** để duyệt bài và reload lại web

# Hướng dẫn sử dụng markdown

Đọc bài này: https://viblo.asia/helps/cach-su-dung-markdown-bxjvZYnwkJZ

**Và** đơn giản chỉ cần [cài typora](https://www.typora.io/) xài cho dễ

## HTML trong markdown

Bạn chỉ cần nhớ một số thứ sau đây

### Kiểu chữ

| HTML                  | Kết quả             |
| --------------------- | ------------------- |
| `<b> in đậm </b>`     | <b> in đậm </b>     |
| `<i> in nghiêng </i>` | <i> in nghiêng </i> |

### Căn lề giữa

```html
<center> Chữ này ở giữa</center>
```

**Kết quả**:


<center>Chữ này ở giữa</center>
### Hình ảnh

```html
<img src='https://upload.wikimedia.org/wikipedia/commons/thumb/4/48/Markdown-mark.svg/800px-Markdown-mark.svg.png' width=300>
```

Tham số gồm

 **src:** dẫn đường link tới bức ảnh

**width:** chiều rộng của bức ảnh

**height:** chiều cao của bức ảnh

<img src='https://upload.wikimedia.org/wikipedia/commons/thumb/4/48/Markdown-mark.svg/800px-Markdown-mark.svg.png' width=300>

### Đính kèm ảnh trong khi viết bài

```html
<center><img src="https://miro.medium.com/max/1200/1*s9raSe9mLeSSuxE3API-ZA.gif" width=400></center>
<center> <b>Ảnh 1</b> Minh họa Object Detection - <i>towardsdatascience </i></center>
```

Lưu ý: Ảnh nên có width từ 300 -> 400 và không nên dài hơn chữ quá 

**Kết quả:**

<center><img src="https://miro.medium.com/max/1200/1*s9raSe9mLeSSuxE3API-ZA.gif" width=400></center>
<center> <b>Ảnh 1</b> Minh họa Object Detection - <i>towardsdatascience </i></center>
# Các thông tin liên hệ

- Thầy Nguyễn Vinh Tiệp: Mentor cho VietCS, hỏi mảng nào thầy cũng chơi

- Nguyễn Trường Phát: Viết bài Computer Vision & Web Owner của VietCS

- Hồ Sỹ Tuyến: Viết bài về Computer Vision & Generative Models
- Lê Thanh Phước Hiếu: Viết bài về các mảng Toán