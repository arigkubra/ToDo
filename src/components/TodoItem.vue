<template>
  <div class="overflow-x-auto w-96 text-white">
    <table class="table">
      <tbody>
        <tr>
          <div class="form-control ">
            <label class="cursor-pointer label">
              <span class="label-text text-white">Remember me</span>
              <input
                type="checkbox"
                checked="checked"
                class="checkbox checkbox-warning"
              />
            </label>
          </div>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  components: "TodoItem",
};
</script>