<template>
    <div class="container mx-auto p-6">
      <h1 class="text-4xl font-bold text-center mb-8 text-gray-800">🏨 Danh Sách Phòng Khách Sạn</h1>
      
      <!-- Bộ lọc -->
      <div class="flex flex-wrap gap-4 justify-center mb-8 bg-gray-200 p-6 rounded-lg shadow-lg">
        <input v-model="filters.name" type="text" placeholder="🔍 Tìm theo tên" class="border p-3 rounded-lg w-60 focus:ring-2 focus:ring-blue-500" />
        <select v-model="filters.type" class="border p-3 rounded-lg w-40 focus:ring-2 focus:ring-blue-500">
          <option value="">Tất cả loại phòng</option>
          <option v-for="type in roomTypes" :key="type" :value="type">{{ type }}</option>
        </select>
        <input v-model.number="filters.guests" type="number" min="1" placeholder="👥 Số lượng khách" class="border p-3 rounded-lg w-40 focus:ring-2 focus:ring-blue-500" />
        <button @click="filterRooms" class="bg-blue-600 text-white px-6 py-3 rounded-lg shadow hover:bg-blue-700 transition-all">🔍 Lọc</button>
      </div>
  
      <!-- Danh sách phòng -->
      <div class="space-y-8">
        <div v-for="(group, index) in groupedRooms" :key="index" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-6">
          <div v-for="room in group" :key="room.id" class="border p-6 rounded-lg shadow-md bg-white hover:shadow-lg transition-all">
            <img :src="room.image" alt="room.name" class="w-full h-48 object-cover mb-4 rounded-lg">
            <h2 class="text-2xl font-semibold text-gray-800 mb-1">🏡 {{ room.name }}</h2>
            <p class="text-gray-600 text-sm">🛏 Loại: <strong>{{ room.type }}</strong></p>
            <p class="text-gray-600 text-sm">👤 Số lượng khách: <strong>{{ room.guests }}</strong></p>
            <p class="text-green-600 font-bold text-lg">💰 {{ room.price.toLocaleString() }} VND/đêm</p>
            <p class="text-gray-500 text-sm">📍 Địa điểm: {{ room.location }}</p>
            <p class="text-yellow-500 text-sm">⭐ {{ room.rating }}/5</p>
            <button class="mt-4 w-full bg-green-500 text-white px-4 py-2 rounded-lg shadow hover:bg-green-600 transition-all text-sm">🛎 Đặt ngay</button>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref, computed } from 'vue';
  
  const rooms = ref([
    { id: 1, name: "Phòng Deluxe", type: "Deluxe", guests: 2, price: 1200000, image: "https://via.placeholder.com/400", location: "Hà Nội", rating: 4.5 },
    { id: 2, name: "Phòng Family", type: "Family", guests: 4, price: 1800000, image: "https://via.placeholder.com/400", location: "TP. Hồ Chí Minh", rating: 4.7 },
    { id: 3, name: "Phòng Standard", type: "Standard", guests: 2, price: 800000, image: "https://via.placeholder.com/400", location: "Đà Nẵng", rating: 4.2 },
    { id: 4, name: "Phòng VIP", type: "VIP", guests: 2, price: 2500000, image: "https://via.placeholder.com/400", location: "Nha Trang", rating: 4.9 },
    { id: 5, name: "Phòng Suite", type: "Suite", guests: 3, price: 2200000, image: "https://via.placeholder.com/400", location: "Huế", rating: 4.8 }
  ]);
  
  const roomTypes = ref(["Deluxe", "Family", "Standard", "VIP", "Suite"]);
  const filters = ref({ name: "", type: "", guests: null });
  
  const filteredRooms = computed(() => {
    return rooms.value.filter(room => {
      return (
        (!filters.value.name || room.name.toLowerCase().includes(filters.value.name.toLowerCase())) &&
        (!filters.value.type || room.type === filters.value.type) &&
        (!filters.value.guests || room.guests >= filters.value.guests)
      );
    });
  });
  
  const groupedRooms = computed(() => {
    const chunkSize = 3;
    return filteredRooms.value.reduce((result, room, index) => {
      const chunkIndex = Math.floor(index / chunkSize);
      if (!result[chunkIndex]) {
        result[chunkIndex] = [];
      }
      result[chunkIndex].push(room);
      return result;
    }, []);
  });
  </script>
  
  <style scoped>
  .container {
    max-width: 1200px;
    margin: auto;
  }
  </style>
  