<template>
  <div class="min-h-screen bg-slate-50">

    <!-- NAVBAR -->
    <nav class="bg-white shadow-sm border-b border-slate-200">
      <div class="max-w-7xl mx-auto px-6 py-4 flex items-center justify-between">
        
        <h1 class="text-lg font-bold text-slate-800 tracking-tight">
          Admin Dashboard
        </h1>

        <div class="flex gap-6 text-xs font-bold uppercase tracking-widest">
          <button
            @click="navigateTo('/home')"
            :class="currentPath === '/home'
              ? 'text-indigo-600 border-b-2 border-indigo-600 pb-1'
              : 'text-slate-400 hover:text-slate-600 transition'"
          >
            Home
          </button>

          <button
            @click="navigateTo('/products')"
            :class="currentPath === '/products'
              ? 'text-indigo-600 border-b-2 border-indigo-600 pb-1'
              : 'text-slate-400 hover:text-slate-600 transition'"
          >
            Inventario
          </button>
        </div>
      </div>
    </nav>

    <!-- CONTENIDO -->
    <div class="max-w-7xl mx-auto px-6 py-10">

      <!-- HOME -->
      <div v-if="currentPath === '/home'" class="space-y-10">

        <!-- Header -->
        <header class="text-center">
          <h2 class="text-4xl font-extrabold text-slate-900 tracking-tight">
            Bienvenido al Panel de Gestión de Marilyn
          </h2>
          <p class="mt-4 text-lg text-slate-600">
            Administra tu inventario y visualiza tus métricas en tiempo real.
          </p>
        </header>

        <!-- Cards de métricas -->
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">

          <!-- Total Productos -->
          <div class="bg-white rounded-2xl shadow-sm border border-slate-200 p-6 hover:shadow-md transition">
            <p class="text-xs uppercase font-bold text-slate-400 tracking-widest">
              Total Productos
            </p>
            <h3 class="mt-3 text-3xl font-extrabold text-slate-900">
              {{ totalProducts }}
            </h3>
          </div>

          <!-- Stock Disponible -->
          <div class="bg-white rounded-2xl shadow-sm border border-slate-200 p-6 hover:shadow-md transition">
            <p class="text-xs uppercase font-bold text-slate-400 tracking-widest">
              Stock Disponible
            </p>
            <h3 class="mt-3 text-3xl font-extrabold text-emerald-600">
              {{ totalStock }}
            </h3>
          </div>

          <!-- Productos Activos -->
          <div class="bg-white rounded-2xl shadow-sm border border-slate-200 p-6 hover:shadow-md transition">
            <p class="text-xs uppercase font-bold text-slate-400 tracking-widest">
              Productos Activos
            </p>
            <h3 class="mt-3 text-3xl font-extrabold text-indigo-600">
              {{ activeProducts }}
            </h3>
          </div>

          <!-- Ingresos -->
          <div class="bg-white rounded-2xl shadow-sm border border-slate-200 p-6 hover:shadow-md transition">
            <p class="text-xs uppercase font-bold text-slate-400 tracking-widest">
              Ingresos
            </p>
            <h3 class="mt-3 text-3xl font-extrabold text-pink-600">
              ${{ totalRevenue }}
            </h3>
          </div>

        </div>

      </div>

      <!-- INVENTARIO -->
      <div v-if="currentPath === '/products'" class="space-y-6">
        <h2 class="text-3xl font-bold text-slate-900">
          Gestión de Inventario
        </h2>

        <p class="text-slate-600">
          Aquí puedes administrar tus productos disponibles.
        </p>

        <!-- Aquí iría tu vista de productos -->
      </div>

    </div>
  </div>
</template>
