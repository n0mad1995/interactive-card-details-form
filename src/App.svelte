<script lang="ts">
  let cardNumber: string = '';
  let cardName: string = '';
  let cardDate: string = '';
  let cardCVV: string = '';

  const CARD_NUMBER_LENGTH = 16;
  const CARD_CVV_LENGTH = 3;
  const CARD_DATE_LENGTH = 5; 

  function handleCardNumberInput() {
    cardNumber = cardNumber.slice(0, CARD_NUMBER_LENGTH);
  }

  function handleCardNameInput() {
    cardName = cardName.slice(0, 50);
  }

  function handleCardDateInput() {
    cardDate = cardDate.slice(0, CARD_DATE_LENGTH);
  }

  function handleCardCVVInput() {
    cardCVV = cardCVV.slice(0, CARD_CVV_LENGTH);
  }
</script>

<style>
  .credit-card-input {
    font-size: 16px;
    padding: 10px;
    margin-bottom: 10px;
  }
</style>

<main>
  <h1>Карта</h1>

  <label>
    Номер карты:
    <input bind:value={cardNumber} type="text" placeholder="Введите номер карты" on:input={handleCardNumberInput} class="credit-card-input" maxlength={CARD_NUMBER_LENGTH} />
  </label>

  <label>
    Имя на карте:
    <input bind:value={cardName} type="text" placeholder="Имя на карте" on:input={handleCardNameInput} class="credit-card-input" maxlength="50" />
  </label>

  <label>
    Дата:
    <input bind:value={cardDate} type="text" placeholder="ММ/ГГ" on:input={handleCardDateInput} class="credit-card-input" maxlength={CARD_DATE_LENGTH} />
  </label>

  <label>
    CVV:
    <input bind:value={cardCVV} type="text" placeholder="CVV" on:input={handleCardCVVInput} class="credit-card-input" maxlength={CARD_CVV_LENGTH} />
  </label>

  <div class="credit-card-input">
    <p>Номер карты: {cardNumber}</p>
    <p>Имя на карте: {cardName}</p>
    <p>Дата: {cardDate}</p>
    <p>CVV: {cardCVV}</p>
  </div>
</main>
