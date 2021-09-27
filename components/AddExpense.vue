<template>
  <div class='add-expense-wrapper'>
    <h1>Add Expense</h1>
    <b-form id="expense-form">
      <b-row class="mb-3">
        <b-col>
          <b-input-group prepend="Date">
            <b-form-datepicker
              v-model='expense.date'
              required
              :date-format-options="{ year: 'numeric', month: '2-digit', day: '2-digit' }" />
          </b-input-group>
        </b-col>
        <b-col>
          <b-input-group prepend="Category">
            <b-form-select v-model="expense.category" :options="categoryOptions" required />
          </b-input-group>
        </b-col>
      </b-row>
      <b-row class="mb-3">
        <b-col>
          <b-input-group prepend="Who paid">
            <b-form-select v-model="expense.whoPaid" :options="whoPaidOptions" required />
          </b-input-group>
        </b-col>
        <b-col>
          <b-input-group prepend="Who pays">
            <b-form-select v-model="expense.whoPays" :options="whoPaysOptions" required />
          </b-input-group>
        </b-col>
      </b-row>
      <b-row>
        <b-col cols="12" sm="6" class="mb-3">
          <b-input-group prepend="Description">
            <b-form-textarea v-model="expense.description" placeholder="Description" rows="1" />
          </b-input-group>
        </b-col>
        <b-col class="mb-3">
          <b-input-group prepend="Amount">
            <b-form-input v-model="expense.amount" type="number" placeholder="Amount..." min="0" step="0.01" required />
          </b-input-group>
        </b-col>
        <b-col cols="3" sm="2" class="submit-button">
          <b-button type="submit" class="float-right">
            Submit
          </b-button>
        </b-col>
      </b-row>
    </b-form>
  </div>
</template>

<script lang="ts">
export default {
  data() {
    return {
      expense: {
        date: new Date().toISOString().slice(0, 10),
        category: '',
        whoPaid: '',
        whoPays: 'Everyone',
        description: '',
        amount: ''
      },
      categoryOptions: [
        {value: '', text: 'Category...', disabled: true},
        'Utilities', 'Groceries', 'Restaurant', 'Other'
      ],
      whoPaidOptions: [
        {value: '', text: 'Who paid...', disabled: true},
        'a', 'b', 'c', 'd'
      ],
      whoPaysOptions: [
        'Everyone', 'a', 'b', 'c', 'd'
      ],
    }
  },
}
</script>

<style lang="scss">
textarea {
  overflow: auto;
}
</style>