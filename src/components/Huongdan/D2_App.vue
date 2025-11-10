<script setup>
    import { ref,reactive } from 'vue'
    const count = ref(0);
    let studentName = ref('hà mạnh khiêm');
    let studentEmail = ref('hakhiem@gmail.com');
    let studentAge = ref(18);
    let studentIsActive = ref(true);

    let HoVaTen = ref('hà mạnh khiêm');

    let state = reactive({amount: 0, name: 'abc'});

    // cứ pháp của ref thường đó là là dữ liệu + .value
    // cứ pháp của reactive đó là state + dữ liệu vd: state.amount
    const increamentCount = () => {
        count.value++;
    }

    const increamentAmount = () => {
        state.amount++;
    }

    const onclickDangKy = () => {
        alert("đăng ký thành công")
    }

    const onclickBlur = () => {
        alert("đăng ký blur");
    }
</script>


<template>
    <h1>Thông tin</h1>
    <table>
        <ul class="list-group">
            <li class="list-group-item">Tên sinh viên: {{ studentName }}</li>
            <li class="list-group-item">Email: {{ studentEmail }}</li>
            <li class="list-group-item">Tuổi: {{ studentAge }}</li>
            <li class="list-group-item">
                Trạng thái học tập:
                {{ studentIsActive ? 'mở cửa' : 'đóng cửa' }}
            </li>
        </ul>
    </table>
    Count: {{ count }}
    <button class="btn btn-warning" @click="increamentCount">IncreamentCount</button>
    Amount: {{ state.amount }}
    <button class="btn btn-danger" @click="increamentAmount">IncreamentAmount</button>

    <hr>
    <h6>2 way data binding</h6>
    <p>Sử dụng đồng bộ dữ liệu từ code js và html</p> 
    <label for="" class="form-label"></label>
    <input type="text" class="form-control" v-model="HoVaTen">
    <!-- khi sử dụng v-model thì mấy cái dữ liệu dù có khai báo bao nhiêu lần nó cũng sẽ thay đổi theo thằng bố v-model 
    chỉ cần sửa phần có v-model là tất cả dữ liệu sẽ sửa theo hết ví dụ sửa dữ liệu trong ô input HoVaTen thì phần 
    dữ liệu xin chào cũng sẽ thay đổi theo -->
    <p>Xin chào: {{ HoVaTen }}</p>

    <h6>Event binding</h6>
    <p>sử dụng để bắt sự kiện</p>
    
    <h3>Bắt sự kiện</h3>
    <button class="btn btn-danger" @click="onclickDangKy">Đăng ký</button>
    <h3>Bắt sự kiện blur</h3>
    <input type="text" class="form-control" @blur="onclickBlur">
</template>