# Chuyển văn bản thành giọng nói qua 3 dòng code

Có thể bạn không tin khi đọc tiêu đề này! sau khi xem đoạn code dưới đây và cái kết "kết tủa"
```javascript
var msg = new SpeechSynthesisUtterance();
msg.text = "Your browser can speak!";
window.speechSynthesis.speak(msg);
```
Bất ngờ phải không nào? Trong bài viết này mình sẽ giải thích cách mà browser chuyển văn bản thành lời nói (Text To Speech) trong javascript nhé!

### Giới thiệu
Text To Speech là phương pháp chuyển văn bản thành giọng nói, văn bản được máy tính đọc hiểu và phát ra âm thanh bằn giọng nói củ robot/người.
Ở đoạn code ví dụ trên, trình duyệt sử dụng phương pháp này từ Web Speech API, con này hỗ trợ cả chuyển văn bản thành giọng nói và chuyển từ giọng nói sang văn bản.
> Speech recognition is not currently supported on all browsers click [here](https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition#Browser_compatibility) for list of compatible browsers.

Tuy nhiên API này chỉ hỗ trợ một số phiên bản trong [danh sách](https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition#Browser_compatibility) này.

### Bắt đầu
Không hỗ trợ hầu hết phiên bản của trình duyệt, vậy làm sao để check nó có hỗ trợ hay không? Cũng dễ thôi mà :)

```javascript
if ('speechSynthesis' in window) {
 // Speech Synthesis supported 🎉
} else {
  // Speech Synthesis Not Supported 😣
  alert("Sorry, your browser doesn't support text to speech!");
}
```

Bước tiếp theo chúng ta tạo mới object `speechSynthesis`, thiết lập cho các thông số như text,... để máy hiểu mình cần nói cái gì? 👇

```javascript
var msg = new SpeechSynthesisUtterance();
msg.text = "Your browser can speak!";
window.speechSynthesis.speak(msg);
```
#### Giải thích
- Dòng 1: Tạo biến `msg` và gán instance của class `speechSynthesis` cho nó
- Dòng 2: Thuộc tính `.text` để nhập văn bản cần chuyển sang giọng nói
- Dòng cuối cùng gọi hàm `.speak()` để browser nói đoạn văn từ thuộc tính `.text`
