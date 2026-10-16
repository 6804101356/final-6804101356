# Final Exam: Software Testing ด้วย Playwright

- ชื่อ-นามสกุล: นันทิชา แปงทา
- รหัสนักศึกษา: 6804101356
- ระบบที่ทดสอบ: https://www.saucedemo.com/

## วิธีรัน
​```bash
npm install
npx playwright install
npx playwright test
npx playwright show-report
​```

## IT-01: Top-Down Integration Testing ด้วย Stub
- **ส่วนที่เป็น Real:** หน้า Login ของ SauceDemo (กรอก standard_user / secret_sauce แล้วเข้า inventory.html จริง)
- **ส่วนที่เป็น Stub:** หน้า Inventory ที่จำลองด้วย `page.setContent()` แสดง `Mock Inventory Ready` และสินค้า `Mock Backpack`, `Mock Bike Light`
- Stub นี้จำลอง DOM ระดับ Browser หลัง Login จริง ไม่ได้แทน Internal Module ของ SauceDemo

## IT-02: Bottom-Up Integration Testing ด้วย Driver
- **Driver:** ฟังก์ชัน `driverOpenInventory()` ตั้ง Cookie `session-username=standard_user` ด้วย `BrowserContext.addCookies()` แล้วเปิด inventory.html ตรง ๆ โดยไม่ผ่านฟอร์ม Login
- **ส่วนที่เป็น Real:** หน้า Inventory (สินค้า 6 รายการ), การเพิ่มสินค้า, Cart Badge และหน้า Shopping Cart ของ SauceDemo จริง