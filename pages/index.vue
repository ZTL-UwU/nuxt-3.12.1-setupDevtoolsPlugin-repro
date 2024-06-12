<template>
  <VeeForm>
    <VeeField name="email" type="email" :rules="fieldSchema" />
    <VeeErrorMessage name="email" />
  </VeeForm>
</template>

<script setup>
import { toTypedSchema } from '@vee-validate/zod';
import * as zod from 'zod';
const fieldSchema = toTypedSchema(
  zod.string().nonempty('Field is required').email('Must be a valid email')
);
</script>
