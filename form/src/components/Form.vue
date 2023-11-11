<template>
    <form id="form-container">
        <div class="section">
            <div class="row">
                <label class="label">Фамилия</label>
                <input type="text" class="input-text" required/> 
            </div>
            <div class="row">
                <label class="label">Имя</label>
                <input type="text" class="input-text" required/> 
            </div>
            <div class="row">
                <label class="label">Отчество</label>
                <input type="text" class="input-text" /> 
            </div>
            <div class="row">
                <label class="label">Дата рождения</label>
                <input type="text" class="input-text" required/> 
            </div>
            <div class="row">
                <label class="label">Номер телефона</label>
                <input type="phone" class="input-text" required/> 
            </div>
            <div class="row">
                <label class="label">Пол</label>
                <input type="radio" name="gender" value="male" class="input-radio"/>
                <label class="label">Мужской</label>
                <input type="radio" name="gender" value="female" class="input-radio" />
                <label class="label">Женский</label>
            </div>
            <div class="row">
                <label class="label">Группа клиентов</label>
                <select class="input-select" multiple required>
                    <option>VIP</option>
                    <option>Проблемные</option>
                    <option>ОМС</option>
                </select> 
            </div>
            <div class="row">
                <label class="label">Лечащий врач</label>
                <select class="input-select">
                    <option>Иванов</option>
                    <option>Захаров</option>
                    <option>Чернышева</option>
                </select> 
            </div>
            <div class="row">
                <label class="label">Не отправлять СМС</label>
                <input type="checkbox" class="input-checkbox" /> 
            </div>
        </div>
        <div style="section">
            <h5 class="section-name">Адрес</h5>
            <div class="row">
                <label class="label">Индекс</label>
                <input type="text" class="input-text" />
            </div>
            <div class="row">
                <label class="label">Страна</label>
                <input type="text" class="input-text" />
            </div>
            <div class="row">
                <label class="label">Область</label>
                <input type="text" class="input-text" />
            </div>
            <div class="row">
                <label class="label">Город</label>
                <input type="text" class="input-text" required />
            </div>
            <div class="row">
                <label class="label">Улица</label>
                <input type="text" class="input-text" />
            </div>
            <div class="row">
                <label class="label">Дом</label>
                <input type="text" class="input-text" />
            </div>
        </div>
        <div class="section">
            <h5 class="section-name">Паспорт</h5>
            <div class="row">
                <select class="input-select" required>
                    <option>Паспорт</option>
                    <option>Свидетельство о рождении</option>
                    <option>Вод. удостоверение</option>
                </select>
            </div>
            <div class="row">
                <label class="label">Серия</label>
                <input type="text" class="input-text" />
            </div>
            <div class="row">
                <label class="label">Номер</label>
                <input type="text" class="input-text" />
            </div>
            <div class="row">
                <label class="label">Кем выдан</label>
                <input type="text" class="input-text" />
            </div>
            <div class="row">
                <label class="label">Дата выдачи</label>
                <input type="text" class="input-text" required />
            </div>
        </div>
        <button id="button">Создать</button>
    </form>
</template>

<script>
export default {
    name: 'Form',
    components: {
        
    }
}
</script>

<style>

</style>