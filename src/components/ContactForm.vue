<template>
<Form @submit="submitContact" :validation-schema="contactFormSchema">
<div class="form-group">
<label for="name">Tên</label>

<Field name="name" type="text" class="form-control" v-
model="contactLocal.name" />

<ErrorMessage name="name" class="error-feedback" />
</div>
<div class="form-group">
<label for="email">E-mail</label>

<Field name="email" type="email" class="form-control" v-
model="contactLocal.email" />

<ErrorMessage name="email" class="error-feedback" />
</div>
<div class="form-group">
<label for="address">Địa chỉ</label>

<Field name="address" type="text" class="form-control" v-
model="contactLocal.address" />

<ErrorMessage name="address" class="error-feedback" />
</div>
<div class="form-group">
<label for="phone">Điện thoại</label>

<Field name="phone" type="tel" class="form-control" v-
model="contactLocal.phone" />

<ErrorMessage name="phone" class="error-feedback" />
</div>
<div class="form-group form-check">

<input name="favorite" type="checkbox" class="form-check-input" v-
model="contactLocal.favorite" />

<label for="favorite" class="form-check-label">
<strong>Liên hệ yêu thích</strong>
</label>
</div>
<div class="form-group">
<button class="btn btn-primary">Lưu</button>
<button v-if="contactLocal._id" type="button" class="ml-2 btn btn-danger"

@click="deleteContact">
Xóa
</button>
<button type="button" class="ml-2 btn btn-danger" @click="Cancel">
Thoát
</button>
</div>
</Form>
</template>
<script>
import * as yup from "yup";