+++
date = "2016-08-21T11:26:34+07:00"
title = "Hướng dẫn dùng Hugo để viết blog"

+++

Trong bài viết này mình sẽ hướng dẫn sử dụng  Hugo để viết bài. Các bạn cũng sử dụng Hugo để viết bài cho Golangvn. Mình hoan nghênh mọi sự đóng góp từ các bạn. Các bạn có thể sử dụng chức năng pull requests của Github, mình sẽ merge và phản hồi sớm nhất.

<!--more-->

## Bước 1: Cài đặt Hugo
Có nhiều cách để cài đặt Hugo. Cách đơn giản nhất là sử dụng sự hỗ trợ có sẵn của hệ điều hành bạn đang sử dụng:

 - [Cài đặt Hugo trên OS X](https://gohugo.io/tutorials/installing-on-mac/)
 - [Cài đặt Hugo trên Windown](https://gohugo.io/tutorials/installing-on-windows/)
 
Nếu bạn sử dụng Linux có thể tìm kiếm với Package Manager. Trên máy mình sử dụng Arch, vì vậy có thể sử dụng sự hỗ trợ từ `yaourt`
```
$ yaourt -Ss hugo
aur/hugo 0.16-1 (40) (2.46)
    Fast and Flexible Static Site Generator in Go
aur/hugo-git v0.15.r3.g26af48a-1 (1) (0.05)
    Fast and Flexible Static Site Generator in Go
aur/hugo-src 0.16-2 (1) (0.58)
    Fast and Flexible Static Site Generator in Go — built from source.
```

Cá nhân mình chọn cách cài đặt từ mã nguồn của Hugo từ Github. Bạn chỉ cần có Git và Go ở trên máy và sử dụng lệnh `go get`

```
$ go get -v github.com/spf13/hugo
```

Khi đã cài đặt xong bạn có thể chạy thử lệnh `hugo`
```
$ hugo version
Hugo Static Site Generator v0.17-DEV BuildDate: 2016-08-21T00:28:22+07:00
```

## Bước 2: Tạo blog
> Nếu bạn muốn đóng góp trực tiếp bài viết lên Golangvn, bạn có thể bỏ qua bước 2 và 3. Bạn chỉ cần clone [blog trên Github](https://github.com/golangvn/blog) và chuyển qua bước 4.

Khi Hugo đã được cài đặt trên máy của bạn thì mọi chuyện còn lại rất đơn giản. Để tạo một blog mới, bạn sử dụng lệnh `hugo new site`. Ví dụ mình tạo một Hugo site `blog`, mình chạy lệnh
```
$ hugo new site blog
```
Di chuyển vào thư mục `blog` vừa mới tạo, bạn sẽ thấy Hugo tạo cho chúng ta những tập tin cơ bản
```
.
|-- archetypes
|-- config.toml
|-- content
|-- data
|-- layouts
|-- themes
`-- static

6 directories, 1 file
```
## Bước 3: Theme
Bước tiếp theo chúng ta chúng ta cần một `Hugo theme` để thể hiện blog của mình. Bạn có thể chọn một theme trên [Hugo themes](https://themes.gohugo.io/). Cộng đồng Hugo có đóng góp rất nhiều theme đẹp và miễn phí. Ở đây mình chọn theme [Beautiful Hugo](http://themes.gohugo.io/beautifulhugo/).

Di chuyển vào thư mục themes
```
$ cd themes/
```
Clone theme 
```
$ git clone https://github.com/halogenica/Hugo-BeautifulHugo.git beautifulhugo
```
Trở lại thư mục blog của bạn
```
$ cd ..
```
## Bước 4: Tạo bài viết và viết bài
Để tạo một bài viết, chúng ta sử dụng lệnh `hugo new post/tên-bài-viết.md`
Ví dụ:
```
$ hugo new post/huong-dan-hugo.md
```
Hugo sẽ tạo ra tập tin `huong-dan-hugo.md`
```
content
`-- post
    `-- huong-dan-hugo.md

1 directory, 1 file
```
Với nội dung: 
```
+++
date = "2016-08-21T11:26:34+07:00"
draft = true
title = "huong dan hugo"

+++

```
Bạn có thể sửa tiêu đề và viết vài dòng sau dấu `+++`
## Bước 5: Xem thành quả của mình
Để xem bài viết sẽ được thể hiện ra sao hãy dùng lệnh `hugo serve`
```
$ hugo serve --theme=beautifulhugo --buildDrafts
```
Vì bài viết của bạn đang là bản nháp(`draft = true`) nên chúng ta cần thêm `--buildDrafts` vào câu lệnh.

Bây giờ mở trình duyệt vào xem blog của bạn với link [http://localhost:1313/](http://localhost:1313/)

## Bước 6: Xuất bản bài viết
Để chia sẻ bài viết bạn có thể sử dụng Github, Bitbucket hoặc có thể tải lên server của riêng bạn. Ở đây mình sử dụng Github với [Github Pages](https://pages.github.com/)

Bạn có thể làm theo hướng dẫn trên trang của Hugo: [Hosting on GitHub Pages](https://gohugo.io/tutorials/github-pages-blog/
)

Và trang bạn đang đọc chính là thành quả của bài viết này.
