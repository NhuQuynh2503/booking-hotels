<template>
  <div class="content relative">
    <div class="hero text-center min-h-[350px] flex flex-col justify-center bg-[#1e3a8a]">
      <h1 class="text-3xl text-white font-bold">Tìm & đặt phòng khách sạn với <br />các bước đơn giản!</h1>
      <p class="text-lg text-white mt-2">Khám phá ngay những ưu đãi tốt nhất dành cho bạn tại <b>Booking</b>!</p>
    </div>
    
    <div class="search-box grid grid-cols-1 md:grid-cols-5 gap-4 p-4 bg-white shadow-lg 
    w-10/12 md:w-3/4 mx-auto absolute top-80 left-0 right-0 border border-gray-300 rounded-lg">
      <div class="input-group flex flex-col">
        <label class="font-semibold">Địa điểm tên khách sạn</label>
        <input type="text" placeholder="Nhập địa điểm hoặc tên khách sạn" class="border p-2 rounded-md" />
      </div>
      <div class="input-group flex flex-col">
        <label class="font-semibold">Ngày nhận phòng</label>
        <input type="date" class="border p-2 rounded-md" />
      </div>
      <div class="input-group flex flex-col">
        <label class="font-semibold">Ngày trả phòng</label>
        <input type="date" class="border p-2 rounded-md" />
      </div>
      <div class="input-group flex flex-col">
        <label class="font-semibold">Số lượng</label>
        <input type="number" min="1" value="1" class="border p-2 rounded-md" />
      </div>
      <button  class="search-btn bg-orange-400 text-white py-1 px-2 text-sm rounded-md hover:bg-orange-300">Tìm kiếm</button>
    </div>
    
    <div class="destination-section py-10">
      <h2 class="text-2xl font-bold text-center">ĐIỂM ĐẾN NỔI BẬT</h2>
      <div class="destination-list grid grid-cols-2 md:grid-cols-3 lg:grid-cols-5 gap-4 mt-6">
        <div class="destination-item bg-white shadow-lg p-2 rounded-lg">
          <img src="https://booking.muongthanh.com/upload_images/images/H%60/cau-vang-da-nang.jpg" alt="Đà Nẵng" class="rounded-md" />
          <div class="destination-title font-semibold text-center mt-2">Đà Nẵng</div>
        </div>
        <div class="destination-item bg-white shadow-lg p-2 rounded-lg">
          <img src="https://nld.mediacdn.vn/291774122806476800/2024/8/16/tp-65-1723817004792851519414.jpg" alt="TP. Hồ Chí Minh" class="rounded-md" />
          <div class="destination-title font-semibold text-center mt-2">TP. Hồ Chí Minh</div>
        </div>
      </div>
    </div>
    
    <div class="hotel py-10">
      <h2 class="text-2xl font-bold text-center">Khách sạn nổi bật</h2>
      <div class="hotel-grid grid grid-cols-1 md:grid-cols-3 lg:grid-cols-4 gap-6 mt-6">
        <div class="hotel-card bg-white shadow-lg rounded-lg overflow-hidden">
          <div class="image-wrapper relative">
            <img src="https://motortrip.vn/wp-content/uploads/2022/03/khach-san-da-nang-4-sao-8.jpg" alt="DLG Hotel" class="w-full h-40 object-cover" />
            <span class="absolute top-2 left-2 bg-blue-500 text-white px-2 py-1 text-xs rounded">1.000.000 VNĐ/đêm</span>
          </div>
          <div class="hotel-info p-4">
            <h3 class="text-lg font-semibold">DLG Hotel</h3>
            <p class="text-sm text-gray-500">Thành phố Đà Nẵng</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
