<template>
<div class="ordering">
    <h2>
        Оформить заказ
    </h2>
    <div class="services">
        <label>
            <input type="checkbox" id="cut" name="cut" v-model="cut">
            <span>Порезать дольками</span>
        </label>

        <label>
            <input type="checkbox" id="wrap" name="wrap" v-model="wrap">
            <span>Подарочная упаковка</span>
        </label>

    </div>

    <div class="customer">
        <div>
            <label for="scales">Номер телефона</label>
            <input type="text" id="phone" name="phone"
                   v-model="phone">
        </div>

        <div>
            <label for="scales">Город</label>
            <input type="text" id="city" name="city"
                   v-model="city">
        </div>

        <div>
            <label for="scales">Улица</label>
            <input type="text" id="street" name="street"
                   v-model="street">
        </div>

        <div>
            <label for="scales">Дом</label>
            <input type="text" id="house" name="house"
                   v-model="house">
        </div>
    </div>


    <div class="last">
        <div class="date">
            <label for="date">Выберите дату и время доставки</label>
            <input type="datetime-local" id="date" name="date"
                v-model="date" 
                :min="minDate"
                :max="maxDate"
            >
        </div>

        <button @click="seveResult()">
            Заказать
        </button>
    </div>
        
</div>
</template>

<script>
export default {
  name: 'Ordering',
  props: ['prop_cut', 'prop_wrap'],
  data() {
        return {
            cut: '',
            wrap: '',
            phone: '',
            city: '',
            street: '',
            house: '',
            date: '',
            minDate: "2022-04-29T00:00",
            maxDate: "2022-06-29T00:00",
        }
  },
  created() {
      let today = new Date();
        let dd = today.getDate();
        let mm = today.getMonth() + 1;
        let yyyy = today.getFullYear();
        let minutes = today.getMinutes();
        let hour = today.getHours() + 1;

        if(dd < 10) dd='0' + dd
        if(mm < 10) mm='0' + mm
        if(hour < 10) hour='0' + hour
        if(minutes < 10)minutes='0' + minutes

        let min = yyyy + '-' + mm + '-' + dd + 'T' + hour + ':' + minutes;
        this.minDate = min;

        let maxDD = today.getDate() + 9;
        if(maxDD > 30){
            maxDD = maxDD - 31
            mm++;
        } 
        if(maxDD < 10) maxDD='0' + maxDD

        if(mm < 10) mm='0' + mm

        let max = yyyy + '-' + mm + '-' + maxDD + 'T' + hour + ':' + minutes;
        this.maxDate = max;

        
        console.log("Worked");
  },
  methods: {
        saveResult(){

        }
  },
  watch: {
      cut() {
        this.$emit('cut_wrap', {
            cut: this.cut,
            wrap: this.wrap
        });
      },
      wrap() {
        this.$emit('cut_wrap', {
            cut: this.cut,
            wrap: this.wrap
        });
      },

      prop_cut(){
          this.cut = this.prop_cut;
      },

      prop_wrap(){
          this.wrap = this.prop_wrap;
      }
  }
}
</script>

<style scoped>
.ordering {
    margin-top: 50px;
    text-align: left;
    padding: 40px;
    border-radius: 10px;
    -webkit-box-shadow: 8px 7px 30px -10px rgba(30, 39, 35, 0.31);
    -moz-box-shadow: 8px 7px 30px -10px rgba(30, 39, 35, 0.31);
    box-shadow: 8px 7px 30px -10px rgba(30, 39, 35, 0.31);

    font-size: 20px;
}
h2 {
    margin: 0;
    color: #309A00;
    margin-bottom: 35px;
}
.services span{
    margin-left: 10px;

}
.services label{
    margin-bottom: 10px;
    -moz-user-select: none;
    -khtml-user-select: none;
    user-select: none;     
}

.services label:last-child{
    margin-left: 45px;
}
.customer {
    margin-top: 30px;
    display: flex;
    flex-wrap: wrap;
}
.customer div {
    display: flex;
    flex-direction: column;
    width: 50%;
    margin-bottom: 15px;
}
.customer input{
    margin-top: 5px;
    width: 85%;
    height: 25px;
}

input[type=text], input[type=datetime-local]{
  border: 1px solid #309A00;
  border-radius: 4px;
  padding-left: 8px;
  font-size: 18px;
}

.date input{
    cursor: pointer;
    margin-top: 5px;
    width: 60%;
    height: 25px;
}
.date {
    margin-top: 5px;
}

.last {
    display: flex;
    align-items: flex-end;
    justify-content: space-between;
}

button {
    cursor: pointer;
    background: #309A00;
    border: none;
    color: #fff;
    border-radius: 5px;
    font-size: 25px;
    padding: 5px 10px;
    margin-right: 25px;
}

button:hover {
    background: #2e7a0a;
}
</style>
