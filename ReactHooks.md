### mouted và unmouted
- mouted: là lúc component được đưa vào sử dụng
- unmounted: là lúc mình gỡ component đó ra khỏi ứng dụng react,ko sử dụng đến nó nữa
### ---- useState(initialValue) ---
- Sử dụng khi muốn render lại giao diện nếu có dữ liệu thay đổi
- Component sẽ được rerender sau khi hàm setState chạy
- Initial value chỉ được dùng cho lần render đầu tiên
- useState nhận vào initial value, trả ra mảng 2 phần tử [state, setState]
- hàm setState có thể nhận vào 1 call back. param là state trước đó setState(previousState => {do something})
- hàm useState có thể nhận vào 1 callback, và lấy giá trị trả về của callback để làm initial value

### ---- useEffect(callback, [dependencies]) ---
- Được sử dụng khi cần các side effect
- Cần hiểu rõ add/remove event listener, observer pattern : subscribe, unsubscribe, closure, ===, call api
- useEffect thường được sử dụng để update DOM, Call API, Listen DOM event, Clean up: subscribe, unsubscribe
- Chung: callback luôn được gọi khi component được mounted
- TH `useEffect(callback)`: callback được gọi khi component rerender
- TH `useEffect(callback, [])`: Chỉ gọi callback 1 lần khi component mounted
- TH `useEffect(callback, [deps])`: Được gọi lại khi deps thay đổi
- Cleanup function luôn được gọi trước khi component được unmounted
- Cleanup function luôn được gọi trước khi callback được gọi (trừ lần component được mounted)
- Cleanup function là hàm được return ra từ useEffect()
- Cleanup function được sử dụng khi component có thể bị unmouted mà component đó có sử dụng setInterval, setTimeOut, async, listener event, subscriber event

### ---- useLayoutEffect() ---
- Gần như tương tự với useEffect. Khác nhau ở chỗ thứ tự thực hiện. Hiếm khi dùng thằng này
### memo
- Higher order component (HOC)
- memo giúp ghi nhớ các props của component để tránh việc rerender ko cần thiết khi các props ko thay đổi
### ---- useCallback() ---
- Thường sử dụng kèm với memo()
- Khi component cha truyền cho component con 1 props dạng tham chiếu, với mỗi lần rerender sẽ tạo ra 1 tham chiếu mới => dẫn đến component con bị rerender. Nhưng mình muốn chỉ có 1 tham chiếu được dùng kể cả khi bị render component cha thì props đó vẫn có 1 địa chỉ bộ nhớ => useCallback(callback, []), 
- deps và callback hoạt động giống như useEffect()

### ---- useMemo() ---
- giúp tránh thực hiện lại 1 logic nào đó không cần thiết
- useMemo nhận vào 1 callback, callback này trả ra 1 kết quả
- useMemo(callback, [deps]): callback sẽ được gọi lại khi deps thay đổi.
- Nếu deps = [] thì useMemo chỉ tính toán 1 lần. ở những lần component được rerender lại thì useMemo trả về giá trị tính toán đó.
### ---- useReducer() ---
### ---- useContext() ---
- Giúp truyền data từ cha đến cháu mà không cần thông qua con
- Tạo 1 context, export ra ngoài => ở nơi nào cần dùng thì import nó vào => AbcContext.Provider, AbcContext.Consumer
- Cách truyền và nhận context giữa cha và cháu
### ---- useRef() ---
- Luu cac gia tri qua 1 ham tham chieu ben ngoai.
- Là 1 hàm trả về 1 plain object có property là "current"
- Nhận vào 1 giá trị khởi tạo
- const xXRef = useRef(): xXRef sẽ được truyền vào 1 property là ref={xXref}. property này chỉ có ở trong DOM thật (thẻ div, p...)
- Hàm useRef chỉ sử dụng giá trị khởi tạo ở lần đầu tiên component được mounted (nếu ko truyền thì là undefined). Còn khi component được render thì hàm này ko sử dựng giá trị init đó nữa
- Có thể lưu DOM element bằng useRef

### ---- useImperativeHandle() ---
- Giúp tuỳ chỉnh 1 ref của function component

### --- forwardRef() ---
- là 1 higer order component
