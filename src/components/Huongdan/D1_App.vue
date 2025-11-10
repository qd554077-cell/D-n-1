<script setup>
    let courseName = "Framework Vue 3";
    let courseLevel = "Nâng cao";
    let courseTime = 30
</script>

<template>
    <div class="container">
        <h1 class="display-4 mb-3">Thông tin</h1>
        <ul class="list-group">
            <li class="list-group-item">
                Tên khóa học: {{ courseName }}
            </li>
            <li class="list-group-item">Cấp độ {{ courseLevel }}</li>
            <li class="list-group-item">Thời gian {{ courseTime }}</li>
            <li class="list-group-item">
                Trạng thái:
                {{ courseIsActive ? 'đang mở' : 'đóng cửa' }}
            </li>
        </ul>
    </div>
</template>