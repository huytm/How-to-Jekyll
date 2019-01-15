#### Lời mở đầu
Bạn là một SysAdmin - Bạn là Developer và muốn ghi chú lại tài liệu của mình? Hay bạn đơn giản chỉ là một người thích viết lách và có một chút ít kiến thức ít ỏi khi sử dụng git và Github (như mình :v) ?

Bạn hoàn toàn có thể sử dụng một nền tảng có sẵn đề  viết biết blog  như [blogspot](https://www.blogger.com/), [wordpress](https://wordpress.com), [netlify](https://www.netlify.com/) hay vân vân và mây mây. Nhưng bạn có biết bản thân Github cũng có một nền tảng hỗ trợ bạn publish một blog không? Đó là một nền tảng khá nổi tiếng, có cộng đồng phát triển lớn, đã support tương đối đầy đủ tính năng để bạn có thể phát triển một trang blog cho riêng mình. Là một  nền tảng không cầu kỳ, nhỏ gọn, customize dễ dàng (nếu bạn biết một chút về html, css) và có performace khá tốt. Và nền tảng mình muốn nói tới ở đây chính là [Github Pages](https://pages.github.com/). 

Trong phạm vi bài viết này mình không so sánh sự khác biệt giữa các nền tảng dùng để viết blog, cái nào tốt hơn cái nào, cái nào đẹp hơn cái nào mà mình chỉ  viết một tài liệu nho nhỏ cho bản thân, cũng như chia sẻ với những ai muốn sử dụng Github Pages nhưng chưa biết bắt đầu từ đâu.

Bài viết gồm bốn phần chính là:
- Giới thiệu về Github Pages.
- Cơ chế hoạt động của Github Pages
- Tự tạo một blog với Github Pages.
- Sử dụng một theme có sẵn cho blog.

### 1. GIỚI THIỆU VỀ GITHUB PAGES

_Github pages là một web hosting service được phát triển bởi Github để lưu trữ các trang web tĩnh phục vụ cho việc viết blog, tài liệu cho dự án, hoặc thậm chí là viết sách_ (Nguồn wiki).

Github pages chủ yếu dựa trên nền tảng phần mềm [Jekyll](https://jekyllrb.com/) - một nền tảng viết bằng Ruby được phát triển bởi [Tom Preston-Werner](https://en.wikipedia.org/wiki/Tom_Preston-Werner). Jekyll release phiên bản đầu tiên của mình năm 2008, và sau đó được Parker Moore tiếp quản. Tính đến năm 2017, Jekyll đã là trình tạo web tĩnh phổ biến nhất thế giới và phần lớn là do Github áp dụng. 

>Có thể bạn biết rồi: cha đẻ của Jekyll là Tom Preston-Werner cũng chính là người đồng sáng lập ra Github.

Tính đến thời điểm tháng 04/01/2019. Jekyll đã release đến phiên bản 3.8.5 và Github pages sử dụng phiên bản stable-Jekyll là 3.7.4. 

Cộng đồng của Jekyll cũng rất lớn, khoảng 8000 contributor chính thức và hàng nghìn người sử dụng ở khắp nơi trên thế giới. Điều đó cũng có thể đánh giá rằng, Jekyll là một sản phầm đáng để sử dụng đấy chứ.

![alt text](https://raw.githubusercontent.com/huytm/How-to-Jekyll/master/images/github-jekyll.png "jekyll gitbug")

>Share link github của Jekyll cho ai muốn trở thành thánh Jekyll (https://github.com/jekyll/jekyll)

### 2. CƠ CHẾ HOẠT ĐỘNG CỦA GITHUB PAGES

Để  hiểu về cơ chế hoạt động của Github pages trước hết bạn cần phải biết một chút về các khái niệm Ruby, RubyGem, Git, Repository, Branch.
- **[Ruby](https://www.ruby-lang.org/vi/) :** là một ngôn ngữ lập trình nguồn mở, chú trọng cao về hiệu suất. Jekyll được viết bằng Ruby và sử dụng Ruby để thông dịch các file mã nguồn ra html.
- **RubyGems :** là một hệ thống quản lý thư viện (libs-packages-managers) để quản lý các thư viện, các plugin được viết bằng Ruby. Nó cũng tương đương với **npm** của javascript, **mvn** của java, hay **composer** của php.
- **Git :** là hệ thống quản lý mã nguồn phân tán, cha đẻ của Git là Linus Torvalds (thánh này ai làm IT mà khoogn biết thì quả là có lỗi với tiền bối :laughing::laughing:. Đây chính là thánh viết Linux Kernel rồi kết hợp với dự án GNU tạo nên hệ điều hành làm mưa làm gió GNU/Linux).
- **Repository :** Đúng như tên gọi của nó, Repository là một kho chứa. Trong hệ thống quản lý mã nguồn Git, Repository chính là một project, một dự án nơi mọi người phát triển và tập trung code của mình tại đó.
- **Branch :** Trong repository lại chia thành nhiều nhánh. Việc chia nhánh này giúp cho việc quản lý mã nguồn được tốt hơn, ngoài ra còn có các tác dụng khác, tùy vào cách sử dụng của mỗi người. Trong quy trình phát triển phần mềm - đa số, mỗi nhánh gồm các nhiệm vụ khác nhau. Chẳng hạn **master** là một nhánh xuyên suốt sẽ là nhánh để release sản phầm - là nhánh sẵn sàng deploy nhất, nhánh **develope** sử dụng để phát triển, hoặc có những nhánh chỉ để phát triển riêng một tính năng cho sản phẩm chẳng hạn...

Mặc định **Github pages sử dụng repository và mã nguồn ở nhánh master** để triển khai blog.

![alt text](https://raw.githubusercontent.com/huytm/How-to-Jekyll/master/images/model.png "Model")

#### 3. TỰ TẠO MỘT BLOG VỚI GITHUB PAGES

`1. Đăng ký một tài khoản Github và đăng nhập.`

`2. Tạo một repository chứa mã nguồn.`

![alt text](https://raw.githubusercontent.com/huytm/How-to-Jekyll/master/images/blank-step1.png
 "Step1")
 
`3. Chọn tạo "New" để tạo mới.` 

![alt text](https://raw.githubusercontent.com/huytm/How-to-Jekyll/master/images/blank-step2.png
 "Step2")

`4. Đặt tên cho Repository và chọn "Create repository".` 

![alt text](https://raw.githubusercontent.com/huytm/How-to-Jekyll/master/images/blank-step3.png
 "Step3")
 
`5. Tạo một file README để mô tả sơ qua về Repository của bạn.` 

![alt text](https://raw.githubusercontent.com/huytm/How-to-Jekyll/master/images/blank-step4.png
 "Step4")

`6. Nhập mô tả cho Repository vào file README sau đó chọn "Commit new file".` 

![alt text](https://raw.githubusercontent.com/huytm/How-to-Jekyll/master/images/blank-step5.png
 "Step5")

`7. Tạo file "index.html".` 

![alt text](https://raw.githubusercontent.com/huytm/How-to-Jekyll/master/images/blank-step6.png
 "Step6")
 
`8. Nhập nội dung file - vì file có phần mở rộng là html, nên nội dung file sẽ được viết bằng ngôn ngữ html.` 

![alt text](https://raw.githubusercontent.com/huytm/How-to-Jekyll/master/images/blank-step7.png
 "Step7")
 
`9. Publish blog thôi nào !!.` 

![alt text](https://raw.githubusercontent.com/huytm/How-to-Jekyll/master/images/blank-Step8.png
 "Step8")

 `10. Đổi tên repository thành định dạng như sau "any-name.github.io". Trong bài viết này mình để là "huytm.github.io".`
 
 >Một lưu ý nho nhỏ, nếu trong tài khoản github của bạn đã có một repository đã deploy Github Page rồi, thì khi các repository khác khi  deploy tiếp lên Github Pages sẽ là một **URI** của **URL** đã đăng ký trước đó. Ví dụ "http://huytm.github.io/my-another-blog"` 

![alt text](https://raw.githubusercontent.com/huytm/How-to-Jekyll/master/images/blank-step9.png
 "Step9")
 
`11. Kéo xuống một chút bạn sẽ thấy thông báo như sau là thành công rồi đó` 

![alt text](https://raw.githubusercontent.com/huytm/How-to-Jekyll/master/images/blank-step10.png
 "Step10")
 
`12. Truy cập url mà đã lấy được từ bước 11 để xem thành quả` 

![alt text](https://raw.githubusercontent.com/huytm/How-to-Jekyll/master/images/blank-step13.png
 "Step13")
 
 **Tadaaa**

### 4. SỬ DỤNG  MỘT  THEME CÓ SẴN  CHO BLOG

Thường với một người mù mờ về nghệ thuật và code kém như mình thì mình sẽ hay chọn một theme có sẵn cho blog :laughing: :laughing:

Để chọn một theme bất kỳ bạn vào trang này https://jekyllthemes.io/free. Sau đó lựa chọn theme bất kỳ mà mình thích nhé, lưu ý tìm được github của theme đó thì càng tốt :laughing: 

Giả sử mình chọn được **theme** này https://deanattali.com/beautiful-jekyll/ và **github** của nó là https://github.com/daattali/beautiful-jekyll

`1. Đầu tiên hãy folk nó về để nó rẽ nhánh thành một repository của mình đã nhé.`

![alt text](https://raw.githubusercontent.com/huytm/How-to-Jekyll/master/images/step1.png
 "Step1")

`2. Folk xong nó sẽ trông thế này.`

![alt text](https://raw.githubusercontent.com/huytm/How-to-Jekyll/master/images/step2.png
 "Step2")
 
`3. Tiếp theo hãy mô-đi-phê nó để nó trở thành blog của mình.`

![alt text](https://raw.githubusercontent.com/huytm/How-to-Jekyll/master/images/step3.png
 "Step3")
 
`4. Sửa chỗ bôi đỏ này là quan trọng nhất này.`

![alt text](https://raw.githubusercontent.com/huytm/How-to-Jekyll/master/images/step4.png
 "Step4")

`5. Sửa xong thì vào "Setting" trỏ lại cái url cho nó giống như ở hướng dẫn trên.`

![alt text](https://raw.githubusercontent.com/huytm/How-to-Jekyll/master/images/step5.png
 "Step5")
 
`6. Sửa xong thì vào "Setting" đổi tên để nó trỏ lại cái url cho nó giống như ở hướng dẫn trên.`

![alt text](https://raw.githubusercontent.com/huytm/How-to-Jekyll/master/images/step6.png
 "Step6")

`6. Chờ tí cho code đồng bộ lên Github Pages... Sau đó truy cập vào url.`

![alt text](https://raw.githubusercontent.com/huytm/How-to-Jekyll/master/images/step7.png
 "Step7")

**Done**

### TỔNG KẾT

- Bài viết này chỉ là một hướng dẫn nho nhỏ để các bạn sử dụng **Github Pages** viết blog cho riêng mình.
- Để modify những theme có sẵn hay tự build một blog từ đầu còn **phụ thuộc vào khả năng của từng người**.
- Bài viết cũng là bước tiếp cận đầu tiên, giúp cho các bạn có cái nhìn tổng quan  khi sử dụng Github Pages và Jekyll.
- Bài viết có thể còn có sai sót, rất mong nhận được sự đóng góp ý kiến từ các bạn.
- Trong bài tiếp theo mình sẽ viết hướng dẫn deploy Blog trên một con **Local Jekyll** mà không cần phải phụ thuộc vào Github Pages nữa.

### TÀI LIỆU THAM KHẢO

https://en.wikipedia.org/wiki/Jekyll_(software)

https://en.wikipedia.org/wiki/Tom_Preston-Werner

https://github.com/jekyll/jekyll

https://jekyllrb.com/news/releases/
