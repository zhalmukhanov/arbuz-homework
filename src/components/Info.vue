<template>
<div class="info_wrapper">
    <img src="../assets/img/ferma.jpg" alt="farm">
    <div class="card_body">
        <h1>
            Ферма №1
        </h1>
        <p class="description">
            Значимость этих проблем настолько очевидна, что понимание сути ресурсосберегающих технологий играет важную роль в формировании вывода текущих активов. Следует отметить, что синтетическое тестирование позволяет выполнить важные задания по разработке укрепления моральных ценностей. Внезапно, предприниматели в сети интернет представляют собой не что иное, как квинтэссенцию победы маркетинга над разумом и должны быть призваны к ответу.
        </p>

        <div class="info_container">
            <div>
                <p class="info">
                    Количество cпелыех арбузов:
                    <span>
                        75
                    </span>
                </p>
                <p class="info">
                    Рейтинг:
                    <span>
                        4.5
                    </span>
                </p>
            </div>
            
            <div>
                <p class="price">
                    Цена:
                    <span>
                        120 тг/кг.
                    </span>
                </p>
            </div>
        </div>
        
    </div>
</div>
</template>

<script>
export default {
  name: 'Info'
}
</script>

<style scoped>
.info_wrapper {
    padding-top: 50px;
    display: flex;
    justify-content: space-between;
}

img {
    width: 500px;
    border-radius: 10px;
}

.card_body {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 15px;
    padding-left: 30px;
}
h1, p {
    margin: 0;
}

h1 {
    color: #309A00;
    margin-bottom: 10px;
}
.description{
    text-align: left;
}
.info_container {
    width: 100%;
    margin-top: 30px;
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
}
.info {
    text-align: left;
    margin-bottom: 5px;
    font-size: 18px;
    font-weight: 600;
}
.info span{
    color: #309A00;
}
.price {
    margin-left: 20px;
    font-size: 18px;
    font-weight: 600;
}

.price span{
    padding: 5px 10px;
    border-radius: 5px;
    background-color: #FF2600;
    color: aliceblue;
    text-align: right;
    font-weight: 600;
}
</style>
