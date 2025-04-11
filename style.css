<!DOCTYPE html>
<html lang="en" x-data="app()" xmlns="http://www.w3.org/1999/xhtml">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>POS Booking System</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://unpkg.com/alpinejs" defer></script>
</head>
<body class="bg-gray-50 p-4 font-sans" x-init="init()">

  <div class="max-w-6xl mx-auto space-y-8">
    <!-- Table Grid -->
    <div>
      <h2 class="text-2xl font-semibold mb-4">🪑 Table Status</h2>
      <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-5 gap-4">
        <template x-for="table in tables" :key="table.id">
          <div 
            class="p-4 rounded shadow text-center cursor-pointer transition"
            :class="{
              'bg-green-100 text-green-800': table.status === 'available',
              'bg-yellow-100 text-yellow-800': table.status === 'booked',
              'bg-red-100 text-red-800': table.status === 'occupied'
            }"
            @click="selectTable(table.id)">
            <div class="text-lg font-bold">Table <span x-text="table.id"></span></div>
            <div class="text-sm" x-text="table.status"></div>
          </div>
        </template>
      </div>
    </div>

    <!-- Booking Form -->
    <div class="bg-white rounded p-6 shadow">
      <h2 class="text-xl font-semibold mb-4">📅 Booking Form</h2>
      <div class="grid sm:grid-cols-2 md:grid-cols-4 gap-4">
        <div>
          <label class="font-medium block mb-1">Selected Table</label>
          <input type="text" class="w-full border rounded px-3 py-2" :value="selectedTable ? 'Table ' + selectedTable : 'None'" readonly>
        </div>
        <div>
          <label class="font-medium block mb-1">Check-in Time</label>
          <input type="time" class="w-full border rounded px-3 py-2" x-model="checkinTime">
        </div>
        <div>
          <label class="font-medium block mb-1">Check-out Time</label>
          <input type="time" class="w-full border rounded px-3 py-2" x-model="checkoutTime">
        </div>
        <div>
          <label class="font-medium block mb-1">Payment Screenshot</label>
          <input type="file" class="w-full border rounded px-3 py-2">
        </div>
      </div>
      <div class="mt-4 flex flex-wrap gap-3">
        <button class="bg-blue-600 text-white px-5 py-2 rounded hover:bg-blue-700" @click="confirmBooking()">Confirm Booking</button>
        <button class="bg-gray-500 text-white px-4 py-2 rounded">Transfer Table</button>
        <button class="bg-gray-500 text-white px-4 py-2 rounded">Split Table</button>
        <button class="bg-gray-500 text-white px-4 py-2 rounded">Combine Tables</button>
        <button class="bg-red-500 text-white px-4 py-2 rounded">Cancel Booking</button>
      </div>
    </div>
  </div>

  <script>
    function app() {
      return {
        tables: [],
        selectedTable: null,
        checkinTime: '',
        checkoutTime: '',

        init() {
          // Simulated table data
          this.tables = [
            { id: 1, status: 'available' },
            { id: 2, status: 'booked' },
            { id: 3, status: 'occupied' },
            { id: 4, status: 'available' },
            { id: 5, status: 'occupied' }
          ];
        },

        selectTable(id) {
          this.selectedTable = id;
        },

        confirmBooking() {
          if (!this.selectedTable || !this.checkinTime || !this.checkoutTime) {
            alert("Please select a table and set both times.");
            return;
          }

          const table = this.tables.find(t => t.id === this.selectedTable);
          if (table) {
            table.status = 'booked';
            alert(`Booking confirmed for Table ${this.selectedTable} from ${this.checkinTime} to ${this.checkoutTime}`);
          }
        }
      }
    }
  </script>

</body>
</html>
