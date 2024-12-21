# AutoDenyPostGroup

(function clickAndScroll() {
    // Tìm tất cả các nút có class được chỉ định
    const buttons = document.querySelectorAll('div[class="x9f619 x1n2onr6 x1ja2u2z x78zum5 xdt5ytf x193iq5w xeuugli x1r8uery x1iyjqo2 xs83m0k xsyo7zv x16hj40l x10b6aqq x1yrsyyn"] div[aria-label="Từ chối"][role="button"]');

    if (buttons.length === 0) {
        console.log("Không tìm thấy nút. Đang cuộn xuống để tải thêm nội dung...");
        window.scrollTo(0, document.body.scrollHeight); // Cuộn xuống cuối trang

        // Đợi 2 giây để nội dung mới tải xong, sau đó kiểm tra lại
        setTimeout(clickAndScroll, 2000);
        return;
    }

    // Bấm vào tất cả các nút tìm thấy
    buttons.forEach(button => {
        button.click();
        console.log("Đã bấm nút:", button);
    });

    // Gọi lại chính nó sau 500ms để kiểm tra tiếp
    setTimeout(clickAndScroll, 500);
})();
