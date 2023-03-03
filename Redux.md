### Redux
* Store: là 1 object, nơi lưu trữ tất cả các state, store chứa các reducers
    - Tạo 1 store bằng cách gọi createStore. Và truyền những reducer mà store ni quản lý
* **Reducer**: là 1 function. nhận vào 2 tham số là state : any và action: {}, dựa vào action.type để từ state cũ tạo ra state mới và trả về
* **Action**: là 1 object. mỗi action có 1 type và thường thì sẽ có 1 payload dùng để gửi cho reducer để reducers dựa vào đó thay đổi state.
    - Ngoài ra object mà action trả về còn chứa property là "payload". Payload ni có giá trị là array, object, string ... payload được reducer lấy để thực hiện công việc trả về state mới
* **Action creatror** : đây là 1 function. function này trả về 1 action
* **Dispatch**: là 1 function, tham số truyền vào của dispatch là 1 action. Khi mô muốn gọi 1 action mô đó. Thì mình truyền action nớ dô trong dispatch(). Hàm dispatch hắn bắn đi 1 action cho store
