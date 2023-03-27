### Overview
- Sử dụng template chuẩn của html không sinh thêm code
- Sử dụng DOM ảo và reactivity để quản lý sự thay đổi trên đối tượng

### Props

- v-bind: thẻ a
- v-one: không ghi đè lại giá trị biến đang hiển thị bằng giá trị mới cập nhật
- v-html: để biên dịch nội dung html từ dạng dữ liệu thô qua dạng html thuần

![](https://i.ibb.co/KX5crGS/image.png)

### Listen Event

- v-model: sử dụng toàn cục có phạm vi nằm trong thẻ cha

### Computed
- Xử lý các công việc một cách độc lập
- Những function ở trong computed thực hiện tác vụ như một function nhưng chỉ được coi như một property 
- Được xử lý chạy trước methods vaf trước khi dữ liệu được load

![](https://i.ibb.co/jZTPtrJ/image.png)

### Watch

- Lắng nghe sự thay đổi của một property

![](https://i.ibb.co/6r0T2b1/image.png)

### Instance (createdApp)

- Có thể tạo được nhiều instance 
- Các thuộc tính trong từng instance là riêng rẽ không ảnh hưởng tới nhau
- Khi tạo giá trị ngoài instance sẽ không được theo dõi bởi instance đó (tạo getter and setter) nhưng vẫn có thể  truy cập được từ bên trong instance

![](https://i.ibb.co/JmhB5Cr/image.png)

### Cách thức hoạt động giữa Vue và DOM

- Vue làm việc với DOM thông qua Virtual DOM 
- 2 đối tượng này lắng nghe lẫn nhau nếu có sự thay đổi sẽ cập nhật lại DOM

![](https://i.ibb.co/2gjxxRt/image.png)

### Lifecyle

![](https://i.ibb.co/rmDhNK7/image.png)

![](https://i.ibb.co/SdDvdNG/image.png)

### Multiple lifecycle

![](https://i.ibb.co/D5b3Z3f/image.png)

### Development Flow

- Load tất cả các template
- Tìm và load các instance và xử lý các tác vụ bên trong

![](https://i.ibb.co/fDWZ9Lr/image.png)

### Custom Directive
[Link documentation](https://vuejs.org/guide/reusability/custom-directives.html)

![](https://i.ibb.co/m5Vtqq1/image.png)

![](https://i.ibb.co/682k1Gv/image.png)

![](https://i.ibb.co/C9p1MRb/image.png)

### Mixins
- Dùng để lưu lại các giá trị dùng chung giữa các component để tái sử dụng
- Mixins được khởi chạy trước các phương thức khởi tạo của component sử dụng lại nó
- Nó là một component mở rộng
- Những dữ liệu được chia sẻ cho các component con từ mixins thì khi các component con có sự thay đổi dữ liệu đó thì vẫn không ảnh hưởng đến component con khác

### Transition

- Sẽ áp dụng animation vào 1 element khi nó được thêm vào hoặc remove ra khỏi DOM
- Bao gồm 2 thành phần: enter và leave 
- Thư viện animation css: [Link](https://animate.style/)

### Interceptor

- Interceptor có thể hiểu như một bước tường lưới chặn các request, response của ứng dụng để cho phép kiểm tra, thêm vào header hoặc thay đổi các param của request, response. Nó cho phép chúng ta kiểm tra các token ứng dụng, Content-Type hoặc tự thêm các header vào request. Điều này cho phép chúng ta tận dụng tối đa thao tác chỉnh sửa header, body, param request gửi lên server sao cho hợp lý nhất, bảo mật nhất. 

[Link axios interceptor](https://www.npmjs.com/package/axios#interceptors)

### Hash fragments
- Tự động chuyển đến tiêu đề có Id=???

### Vue-route
- beforeEach làm việc giống middleware
- Trong component: dùng beforeRotuteEnter check request tới, beforeRouteLeave check request ra khỏi trang đang hiển thị

### VueX
- Vuex là một thư viện quản lý trạng thái (state management) cho ứng dụng VueJS hoạt động dựa trên mô hình Store

- Giao tiếp dữ liệu giữa các component khắc phục hạn chế của event bus chỉ truyền được dữ liệu kiểu data 
- Mutations được sử dụng để thay đổi trạng thái (state) của Vuex, 
- Getters được sử dụng để lấy dữ liệu từ state một cách dễ dàng hơn. 
=> Mutations chỉ có thể được kích hoạt bởi hành động (actions), trong khi Getters có thể được sử dụng trực tiếp trong các thành phần (components).
- Actions được sử dụng để thực hiện các tác vụ bất đồng bộ hoặc không liên quan đến thay đổi trực tiếp trạng thái của state và có thể gọi các mutations để thay đổi state.
- Dispath - Commit

![](https://i.ibb.co/zN0V2xR/image.png)

![](https://i.ibb.co/mcgmTyt/image.png)

### Teleport

- Render data vào trong vị trí của thẻ được chỉ định

### Composition API

- Những thay đổi
![](https://i.ibb.co/4NmH71h/image.png)
- ref thường sử dụng cho dữ liệu dạng không phải object như String, Number, Boolean,... do phải truy cập qua value
- Còn reactive có thể truy cập trực tiếp vào property  
- Khi ref sử dụng là object thì có thể ghi đè bằng 1 object mới còn reactive thì không, nó chỉ có thể thay đổi được giá trị của từng property trong nó
- watchEffect giống như computed nhưng khi thực hiện xong nó sẽ không có giá trị trả về