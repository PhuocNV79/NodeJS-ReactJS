### mouted và unmouted
- mouted: là lúc component được đưa vào sử dụng
- unmounted: là lúc mình gỡ component đó ra khỏi ứng dụng react,ko sử dụng đến nó nữa
### ---- useState(initialValue) ---
- Sử dụng khi muốn render lại giao diện nếu có dữ liệu thay đổi
- Component sẽ được rerender sau khi hàm setState chạy
- Initial value chỉ được dùng cho lần render đầu tiên
- useState nhận vào initial value, trả ra mảng 2 phần tử [state, setState]
- hàm setState có thể nhận vào 1 call back. param là state trước đó setState(pre => {do something})
- hàm useState có thể nhận vào 1 callback, và lấy giá trị trả về của callback để làm initial value

### ---- useEffect(callback, [dependencies]) ---
- Được sử dụng khi cần các side effect
- Cần hiểu rõ add/remove event listener, observer pattern : subscribe, unsubscribe, closure, ===, call api
- useEffect thường được sử dụng để update DOM, Call API, Listen DOM event, Clean up: subscribe, unsubscribe
- callback luôn được gọi khi component được mounted
- TH useEffect(callback): callback được gọi khi component rerender

### ---- useLayoutEffect() ---
### ---- useCallback() ---
### ---- useMemo() ---
### ---- useReducer() ---
### ---- useContext() ---
### ---- useImperativeHandle() ---
### ---- useDebugValue() ---
### ---- useRef() ---
- Là 1 hàm trả về 1 plain object có property là "current"
- Nhận vào 1 giá trị khởi tạo
- Hàm useRef chỉ sử dụng giá trị khởi tạo ở lần đầu tiên component được mounted (nếu ko truyền thì là undefined). Còn khi component được render thì hàm này ko sử dựng giá trị init đó nữa
- 


### ---- useRef() ---
