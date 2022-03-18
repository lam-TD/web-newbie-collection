**Hello 500 anh em**

Phiên bản mình đang tìm hiểu là react-router-dom-v6 nhé.

#Install 

*npm*

`npm install react-router-dom@6`

*Yarn*

`yarn add react-router-dom@6`

#Setup

Để React Router hoạt động trong một ứng dụng, cần render một router gần với root component trong ứng dụng react. React cung cấp một vài routers phụ thuộc vào môi trường dự án đang triển khai.

* `<BrowserRouter>` nên được sử dụng khi chạy trong trình duyệt web (Có thể tùy chỉnh url theo ý muốn)
* `<StaticRouter>` nên sử dụng khi server render một website
* `<NativeRouter>` nên sử dụng trong React Native apps

Một số khái niệm cần nắm:

`<BrowserRouter>` là nơi chứa tất cả route component trong ứng dụng.

```ecmascript 6
import * as React from "react";
import * as ReactDOM from "react-dom";
import { BrowserRouter } from "react-router-dom";

ReactDOM.render(
    <BrowserRouter>
        {/* The rest of your app goes here */}
    </BrowserRouter>,
    root
);
```

`<Routers>` và `<Router>`

`<Link>`

Điều hướng giữa các trang khác nhau, trong react-router-dom một `<Link>` sẽ render ra một thẻ `<a>` và sẽ di chuyển đến `<Route>` có `path` tương ứng với `to` trong props của `<Link>` đó. Tuy nhiên khác với thẻ `<a>` thông thường, khi click vào `<Link>` sẽ không cần refresh lại browser. Nếu muốn thể a hoạt động bình thường(refresh lại browser) bạn có thể sủ dụng `<Link reloadDocument>`

````ecmascript 6
import * as React from "react";
import { Link } from "react-router-dom";

function UsersIndexPage({ users }) {
  return (
    <div>
      <h1>Users</h1>
      <ul>
        {users.map((user) => (
          <li key={user.id}>
            <Link to={user.id}>{user.name}</Link>
          </li>
        ))}
      </ul>
    </div>
  );
}
````
