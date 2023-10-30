---
title: "Everything I learn about Api Gateway"
date: 2022-11-24
draft: false
tech_tags: ["api gateway"]
status: "evergreen"
weight: 2
summary: "This is all things I know about Api Gateway when i was working with this term" 
links:
    external_link:
        text: "Some external link"
        icon: "fas fa-external-link-alt"
        href: "#"
        weight: 1
    another_link:
        text: "Another github link"
        icon: "fab alt brands fa-github"
        href: "#"
        weight: 2
---
## The begin
Chào mọi người. Mình là Khang và đây là trang blog mình viết một vài thứ. Hiện mình đang làm tại một công ty công nghệ trong lĩnh vực tài chính. Sở thích là tìm hiểu và ứng dụng những công nghệ vào thực tế. Công việc mình làm đang cần tìm hiểu và sử dụng về stack AWS. Mình nghĩ thật tốt khi có thể sử dụng blog để thuận tiện công việc tim hiểu hơn, cũng như có một hành trình thú vị và chia sẻ với mọi người. Đó cũng là lí do mình bắt đầu những bài blog về các dịch vụ trong AWS.

AWS stack
Vê AWS hay Amazon Web Services, đây là một stack công nghệ cực kì top trong các bên cung cấp dịch vụ Cloud, bên cạnh Google Cloud, Microsoft Azure, Digital Ocean. Ở AWS có rất nhiều dịch vụ Cloud mà các dev có thể dùng ở nhiều dạng: Về tính toán có EC2, lưu trữ có S3, RDS, Elasticached,.. , serveless compution có lambda function, … Còn rất nhiều thứ đằng sau nữa. Mình có nhu cầu vê dịch vụ gì thì hâu như AWS đều có.

## API gateway
Ở trong phần ep1 này. Mình sẽ viết về API gateway, bởi đây là phần trọng tâm mình sử dụng. API gateway là một khái niệm rất phổ biến với các dev. Nói một cách ngắn gọn API gateway là trung gian của một loạt các giao tiếp giữa client với các services phía backend. API gateway sinh ra bởi sự cần thiết của một đầu mối, lưu chuyển các yêu cầu đến đúng services và trả về kết quả cho client. Có thể xem là 1 Proxy.

Với vai trò trung gian. Ngoài việc đóng vai Proxy trong giao tiếp, API gateway còn đảm nhận một vài vai trò như:

Monitoring: Giám sát, quản lý, thống kê, … Giống như là đầu mối của mọi thứ nên biết rất nhiều
Security: Có thể xem lớp bảo mật, xác thực ở ngay API gateway. Chặn 1 lớp trước khi vào các services của backend
Load balancer: Hình như là một cân bằng tải. Giúp phân chia tải tránh quá tải các services backend…

## Proxy và Non-Proxy
Ở API gateway, có 2 dạng thức chính: Proxy và Non-Proxy. Proxy là loại gateway sử dụng để chuyển tiếp các request từ client sang đến backend, và không thực hiện logic hay thay đổi gi đối với thông tin của request, sau khi backend xử lý sẽ trả lại response và response sẽ cũng chuyển tiếp cho client mà không có xử lý thêm. Ngược lại, với Non-Proxy, thông tin của request được biến đổi phù hợp với logic mong muốn, sau đó sẽ chuyển cho backend, backend trả về response, response sẽ được biến đổi và trả về cho client. 2 dạng thức là hai cách có hoặc không can thiệp vào nội dung của request và response.

Xem video này sẽ rõ hơn