<template>
    <div class="container mx-auto px-4 py-10">
      <h2 class="text-3xl font-bold mb-6 text-center">Hạng Phòng</h2>
      <div v-for="roomCategory in roomCategories" :key="roomCategory.id" class="mb-10">
        <h3 class="text-2xl font-semibold mb-4">{{ roomCategory.category }}</h3>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-5 gap-6">
          <div v-for="room in roomCategory.rooms" :key="room.id"
            class="relative overflow-hidden rounded-2xl shadow-lg bg-cover bg-center h-80 transition-transform transform hover:scale-105 pg-20"
            :style="{ backgroundImage: `url(${room.image})` }">
            
            <div class="h-2/3 bg-cover bg-center" :style="{ backgroundImage: `url(${room.image})` }"></div>
            
            
            <div class="h-1/3 bg-black bg-opacity-50 flex flex-col justify-between text-white p-4">
              <h4 class="text-lg font-semibold">{{ room.name }}</h4>
              <p class="text-sm">{{ room.description }}</p>
              <p class="text-lg font-bold mt-2">{{ room.price }}</p>
              <button class="mt-2 bg-yellow-500 text-white px-4 py-2 rounded">Đặt ngay</button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  
  
  
  <script setup>
  import { ref } from 'vue';
  const roomCategories = ref([
    {
      id: 1,
      category: 'Phòng Tiêu Chuẩn',
      rooms: [
        { id: 1, name: 'Standard Room 1', description: 'Phòng tiêu chuẩn rộng rãi.', price: '1,200,000đ/đêm', image: '/assets/images/room-1.jpg' },
        { id: 2, name: 'Standard Room 2', description: 'Tiện nghi cơ bản.', price: '1,300,000đ/đêm', image: '/assets/images/room-2.jpg' },
        { id: 3, name: 'Standard Room 3', description: 'Phòng tiện nghi đầy đủ.', price: '1,350,000đ/đêm', image: '/assets/images/room-3.jpg' },
        { id: 4, name: 'Standard Room 4', description: 'Phòng sạch sẽ, thoải mái.', price: '1,400,000đ/đêm', image: '/assets/images/room-4.jpg' },
        { id: 5, name: 'Standard Room 5', description: 'Thoáng mát, yên tĩnh.', price: '1,450,000đ/đêm', image: '/assets/images/room-5.jpg' },
        { id: 6, name: 'Standard Room 6', description: 'Phòng hiện đại, tiện lợi.', price: '1,500,000đ/đêm', image: '/assets/images/room-6.jpg' },
        { id: 7, name: 'Standard Room 7', description: 'Rộng rãi, thoải mái.', price: '1,550,000đ/đêm', image: '/assets/images/room-7.jpg' },
        { id: 8, name: 'Standard Room 8', description: 'Phòng tiết kiệm, tiện nghi.', price: '1,600,000đ/đêm', image: '/assets/images/room-10.jpg' },
        { id: 9, name: 'Standard Room 9', description: 'Phòng sạch sẽ, tiện nghi.', price: '1,650,000đ/đêm', image: '/assets/images/room-8.jpg' },
        { id: 10, name: 'Standard Room 10', description: 'Phòng rộng rãi, thoải mái.', price: '1,700,000đ/đêm', image: '/assets/images/room-9.jpg' }
      ]
    },
    {
      id: 2,
      category: 'Phòng Cao Cấp',
      rooms: [
        { id: 1, name: 'Deluxe Room 1', description: 'Nội thất sang trọng.', price: '2,500,000đ/đêm', image: '/assets/images/room-1.jpg'  },
        { id: 2, name: 'Deluxe Room 2', description: 'Hướng nhìn biển.', price: '2,600,000đ/đêm', image: '/assets/images/room-2.jpg'  },
        { id: 3, name: 'Deluxe Room 3', description: 'Phòng có tầm nhìn rộng.', price: '2,650,000đ/đêm', image: '/assets/images/room-3.jpg'  },
        { id: 4, name: 'Deluxe Room 4', description: 'Nội thất hiện đại', price: '2,700,000đ/đêm',image: '/assets/images/room-4.jpg'  },
        { id: 5, name: 'Deluxe Room 5', description: 'Phòng sang trọng, tiện nghi.', price: '2,750,000đ/đêm',image: '/assets/images/room-5.jpg'  },
        { id: 6, name: 'Deluxe Room 6', description: 'Không gian sang trọng.', price: '2,800,000đ/đêm', image: '/assets/images/room-6.jpg'  },
        { id: 7, name: 'Deluxe Room 7', description: 'Phòng đẹp với tiện ích', price: '2,850,000đ/đêm', image: '/assets/images/room-7.jpg'  },
        { id: 8, name: 'Deluxe Room 8', description: 'Phòng cao cấp, yên tĩnh.', price: '2,900,000đ/đêm', image: '/assets/images/room-8.jpg'  },
        { id: 9, name: 'Deluxe Room 9', description: 'Phòng rộng, sang trọng.', price: '2,950,000đ/đêm', image: '/assets/images/room-9.jpg'  },
        { id: 10, name: 'Deluxe Room 10', description: 'Phòng tiện nghi, thoải mái.', price: '3,000,000đ/đêm', image: '/assets/images/room-10.jpg'  }
      ]
    },
    {
      id: 3,
      category: 'Phòng Suite',
      rooms: [
        { id: 1, name: 'Suite Room 1', description: 'Không gian rộng rãi', price: '4,500,000đ/đêm', image: '/assets/images/room-1.jpg'  },
        { id: 2, name: 'Suite Room 2', description: 'Ban công lớn hướng biển.', price: '4,800,000đ/đêm', image: '/assets/images/room-2.jpg'  },
        { id: 3, name: 'Suite Room 3', description: 'Tiện nghi sang trọng.', price: '5,000,000đ/đêm', image: '/assets/images/room-3.jpg'  },
        { id: 4, name: 'Suite Room 4', description: 'Phòng rộng rãi,tiện nghi.', price: '5,200,000đ/đêm', image: '/assets/images/room-4.jpg' },
        { id: 5, name: 'Suite Room 5', description: 'Phòng sang trọng.', price: '5,500,000đ/đêm', image: '/assets/images/room-5.jpg'  },
        { id: 6, name: 'Suite Room 6', description: 'Không gian  đẳng cấp', price: '5,800,000đ/đêm',image: '/assets/images/room-6.jpg'  },
        { id: 7, name: 'Suite Room 7', description: 'Phòng tiện nghi, thoải mái.', price: '6,000,000đ/đêm', image: '/assets/images/room-7.jpg'  },
        { id: 8, name: 'Suite Room 8', description: 'Phòng sang trọng', price: '6,200,000đ/đêm', image: '/assets/images/room-8.jpg'  },
        { id: 9, name: 'Suite Room 9', description: 'Phòng cao cấp', price: '6,500,000đ/đêm', image: '/assets/images/room-9.jpg' },
        { id: 10, name: 'Suite Room 10', description: 'Phòng đầy đủ tiện nghi.', price: '6,800,000đ/đêm', image: '/assets/images/room-10.jpg'  } 
      ]
    },
    {
      id: 4,
      category: 'Phòng Tổng Thống',
      rooms: [
        { id: 1, name: 'Presidential Suite 1', description: 'Không gian sang trọng.', price: '10,000,000đ/đêm', image: '/assets/images/room-1.jpg'},
        { id: 2, name: 'Presidential Suite 2', description: 'Trang bị đẳng cấp.', price: '12,000,000đ/đêm', image: '/assets/images/room-2.jpg'},
        { id: 3, name: 'Presidential Suite 3', description: 'Phòng tổng thống xịn.', price: '13,000,000đ/đêm', image: '/assets/images/room-3.jpg'},
        { id: 4, name: 'Presidential Suite 4', description: 'Dịch vụ đặc biệt cao cấp.', price: '14,000,000đ/đêm',image: '/assets/images/room-4.jpg'},
        { id: 5, name: 'Presidential Suite 5', description: 'Phòng sang trọng', price: '15,000,000đ/đêm', image: '/assets/images/room-5.jpg'},
        { id: 6, name: 'Presidential Suite 6', description: 'Không gian rộng rãi', price: '16,000,000đ/đêm', image: '/assets/images/room-6.jpg'},
        { id: 7, name: 'Presidential Suite 7', description: 'Phòng dịch vụ đặc quyền.', price: '17,000,000đ/đêm', image: '/assets/images/room-7.jpg'},
        { id: 8, name: 'Presidential Suite 8', description: 'Tiện nghi cao cấp.', price: '18,000,000đ/đêm', image: '/assets/images/room-8.jpg'},
        { id: 9, name: 'Presidential Suite 9', description: 'Phòng tổng thống đẹp.', price: '19,000,000đ/đêm', image: '/assets/images/room-9.jpg'},
        { id: 10, name: 'Presidential Suite 10', description: 'Phòng cực kỳ sang trọng.', price: '20,000,000đ/đêm', image: '/assets/images/room-10.jpg' }
      ]
    }
  ]);
  
  
  </script>
  
  <style scoped>
  .container {
    max-width: 1200px;
    margin: auto;
  }
  
  .hover\:brightness-110:hover {
    filter: brightness(1.1);
  }
  </style>
  