<script>
function isDateCorrect(date){
    if(new Date(date) > new Date || date.split('.')[0] > 31 || date.split('.')[1] > 12){
        return false;
    }
    return true;
}
export default {
    data () {
        return {
            client: {
                name: '',
                surname: '',
                secondName: '',
                birthDate: '',
                phone: '',
                gender: '',
                group: '',
                doctor: '',
                sendSMS: false,
                adress: {
                    index: '',
                    country: '',
                    region: '',
                    city: '',
                    street: '',
                    building: ''
                },
                document: {
                    type: '',
                    series: '',
                    number: '',
                    delivered: '',
                    deliveryDate: ''
                }
            }
        }
    },
    methods: {
        checkName(){
            if(!this.client.name.trim()){
                return 'Пожалуйста, введите имя';
            }
        },
        checkSurname(){
            if(!this.client.surname.trim()){
                return 'Пожалуйста, введите фамилию';
            }
        },
        checkBirthDate(){
            if(!this.client.birthDate.trim()){
                return 'Пожалуйста, введите дату рождения';
            }
            let dateTemplate = /^\d\d\.\d\d\.\d\d\d\d$/;
            if(!dateTemplate.test(this.client.birthDate.trim())){
                return 'Пожалуйста, введите дату рождения в формате ДД.ММ.ГГГГ';
            }
        },
        checkPhone(){
            if(!this.client.phone.trim()){
                return 'Пожалуйста, введите номер мобильного телефона';
            }
            let phoneTemplate = /^7\d{10}$/;
            if(!phoneTemplate.test(this.client.phone.replace(/[ -\(\)]/g, ""))){
                return 'Пожалуйста, введите корректный номер мобильного телефона';
            }
        },
        checkGroup(){
            if(!this.client.group || this.client.group.length < 1){
                return 'Пожалуйста, выберите группу клиентов';
            }
        },
        checkCity(){
            if(!this.client.adress.city.trim()){
                return 'Пожалуйста, введите город';
            }
        },
        checkDocument(){
            if(!this.client.document.type){
                return 'Пожалуйста, выберите тип документа';
            }
        },
        checkDeliveryDate(){
            if(!this.client.document.deliveryDate.trim()){
                return 'Пожалуйста, введите дату выдачи документа';
            }
            let dateTemplate = /^\d\d\.\d\d\.\d\d\d\d$/;
            if(!dateTemplate.test(this.client.document.deliveryDate.trim())){
                return 'Пожалуйста, введите дату выдачи документа в формате ДД.ММ.ГГГГ';
            }
        }
    },
    name: 'Form',
    components: {

    }
}
</script>

<template>
    <form id="form-container">
        <div class="section">
            <div class="row">
                <label class="label">Фамилия</label>
                <div class="wrapper">
                    <input type="text" class="input-text" required v-model="client.surname" placeholder="Фамилия"/>
                    <p class="errorMessage">{{checkSurname()}}</p>
                </div>
                 
            </div>
            <div class="row">
                <label class="label">Имя</label>
                <div class="wrapper">
                    <input type="text" class="input-text" required v-model="client.name" placeholder="Имя"/>
                    <p class="errorMessage">{{checkName()}}</p>
                </div>
                 
            </div>
            <div class="row">
                <label class="label">Отчество</label>
                <input type="text" class="input-text" v-model="client.secondName" placeholder="Отчество"/> 
            </div>
            <div class="row">
                <label class="label">Дата рождения</label>
                <div class="wrapper">
                    <input type="text" class="input-text" required v-model="client.birthDate" placeholder="ДД.ММ.ГГГГ"/>
                    <p class="errorMessage">{{checkBirthDate()}}</p>
                </div> 
            </div>
            <div class="row">
                <label class="label">Номер телефона</label>
                <div class="wrapper">
                    <input type="phone" class="input-text" required v-model="client.phone" placeholder="7XXXXXXXXXX"/>
                    <p class="errorMessage">{{checkPhone()}}</p>
                </div> 
            </div>
            <div class="row">
                <label class="label">Пол</label>
                <input type="radio" name="gender" value="male" class="input-radio" v-model="client.gender"/>
                <label class="label">Мужской</label>
                <input type="radio" name="gender" value="female" class="input-radio" v-model="client.gender"/>
                <label class="label">Женский</label>
            </div>
            <div class="row">
                <label class="label">Группа клиентов</label>
                <div class="wrapper">
                    <select class="input-select" multiple required v-model="client.group">
                        <option>VIP</option>
                        <option>Проблемные</option>
                        <option>ОМС</option>
                    </select>
                    <p class="errorMessage">{{checkGroup()}}</p>
                </div> 
            </div>
            <div class="row">
                <label class="label">Лечащий врач</label>
                <select class="input-select" v-model="client.doctor">
                    <option>Иванов</option>
                    <option>Захаров</option>
                    <option>Чернышева</option>
                </select> 
            </div>
            <div class="row">
                <label class="label">Не отправлять СМС</label>
                <input type="checkbox" class="input-checkbox" v-model="client.sendSMS"/> 
            </div>
        </div>
        <div class="section">
            <h5 class="section-name">Адрес</h5>
            <div class="row">
                <label class="label">Индекс</label>
                <input type="text" class="input-text" v-model="client.adress.index"/>
            </div>
            <div class="row">
                <label class="label">Страна</label>
                <input type="text" class="input-text" v-model="client.adress.country"/>
            </div>
            <div class="row">
                <label class="label">Область</label>
                <input type="text" class="input-text" v-model="client.adress.region"/>
            </div>
            <div class="row">
                <label class="label">Город</label>
                <div class="wrapper">
                    <input type="text" class="input-text" required v-model="client.adress.city"/>
                    <p class="errorMessage">{{checkCity()}}</p>
                </div>
            </div>
            <div class="row">
                <label class="label">Улица</label>
                <input type="text" class="input-text" v-model="client.adress.street"/>
            </div>
            <div class="row">
                <label class="label">Дом</label>
                <input type="text" class="input-text" v-model="client.adress.building"/>
            </div>
        </div>
        <div class="section">
            <h5 class="section-name">Паспорт</h5>
            <div class="row">
                <label class="label">Тип документа</label>
                <div class="wrapper">
                    <select class="input-select" required v-model="client.document.type">
                        <option>Паспорт</option>
                        <option>Свидетельство о рождении</option>
                        <option>Вод. удостоверение</option>
                    </select>
                    <p class="errorMessage">{{checkDocument()}}</p>
                </div>
            </div>
            <div class="row">
                <label class="label">Серия</label>
                <input type="text" class="input-text" v-model="client.document.series"/>
            </div>
            <div class="row">
                <label class="label">Номер</label>
                <input type="text" class="input-text" v-model="client.document.number"/>
            </div>
            <div class="row">
                <label class="label">Кем выдан</label>
                <input type="text" class="input-text" v-model="client.document.delivered"/>
            </div>
            <div class="row">
                <label class="label">Дата выдачи</label>
                <div class="wrapper">
                    <input type="text" class="input-text" required v-model="client.document.deliveryDate" placeholder="ДД.ММ.ГГГГ"/>
                    <p class="errorMessage">{{checkDeliveryDate()}}</p>
                </div>
            </div>
        </div>
        <button id="button">Создать</button>
    </form>
</template>



<style>
#form-container{
    width: 50dvw;
    min-width: 200px;
    margin-left: 25dvw;
    margin-top:10px;
    border:1px solid lavender;
    background-color:ghostwhite;
    padding-top: 20px;
}

.section{
    margin-left: 20px;
    border-bottom: 1px solid lavender;
    margin-right: 20px;
    padding-bottom: 20px;
}

.section-name{
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    color:mediumslateblue;
    font-size: 17px;
}

.row{
    margin-left: 10px;
    margin-bottom: 5px;
    width: 100%;
    display: flex;
    flex-direction: row;
}

.label{
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    font-size: 15px;
    width: 10dvw;
    min-width: 150px;
}

.input-text{
    border:1px solid lavender;
    border-radius: 5px;
    height:20px;
    font-size: 16px;
    color:dimgrey;
}

.input-select{
    border:1px solid lavender;
    border-radius: 5px;
    color:dimgray;
}

#button{
    margin-left:40%;
    margin-top: 10px;
    margin-bottom: 10px;
    border: 1px solid lavender;
    border-radius: 5px;
    background-color:lightblue;
    height: 30px;
    font-size: 14px;
}

.wrapper{
    justify-content: end;
    width: 100%;  
}

.errorMessage{
    color:red;
    margin-top:0px;
    padding-top:0px;
    font-size: 13px;
}
</style>