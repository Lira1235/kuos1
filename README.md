<html>
<body>
    <h1>我的第一個 GitHub 網頁</h1>
    <p>Hello World!</p>
<div class="upload-section">
    <h2>分享你的七夕粿成果！</h2>
    <p style="text-align: center;">點擊下方按鈕上傳照片並預覽：</p>
    
    <!-- 隱藏原始樣式，用 label 自訂漂亮按鈕 -->
    <label for="imageInput" class="upload-btn">選取照片</label>
    <input type="file" id="imageInput" accept="image/*" style="display: none;">
    
    <div id="preview-container">
        <p id="no-photo" style="color: #ccc; font-size: 16px;">尚未上傳照片</p>
        <img id="preview-img" src="" alt="您的成果照" style="display: none;">
    </div>
</div>
<script>
    const imageInput = document.getElementById('imageInput');
    const previewImg = document.getElementById('preview-img');
    const noPhotoText = document.getElementById('no-photo');

    imageInput.addEventListener('change', function() {
        const file = this.files[0]; // 取得使用者選取的第一個檔案
        if (file) {
            const reader = new FileReader();
            
            // 當檔案讀取完成時執行
            reader.onload = function(e) {
                previewImg.src = e.target.result; // 將圖片路徑設定為讀取結果
                previewImg.style.display = 'block'; // 顯示圖片
                noPhotoText.style.display = 'none'; // 隱藏「尚未上傳」文字
            }
            
            reader.readAsDataURL(file); // 讀取圖片檔案
        }
    });
</script>
</body>
</html>
