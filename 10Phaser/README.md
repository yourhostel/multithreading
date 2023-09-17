# Phaser 
- [ docs.oracle.com ](https://docs.oracle.com/en/java/javase/20/docs/api/java.base/java/util/concurrent/Phaser.html)

- [ ] Phaser реализация шаблона синхронизации [Бар'єр](https://uk.wikipedia.org/wiki/%D0%91%D0%B0%D1%80%27%D1%94%D1%80_(%D0%BF%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D1%83%D0%B2%D0%B0%D0%BD%D0%BD%D1%8F))
- [ ] Phaser — це інструмент для координації між потоками, дозволяє реалізовувати бар'єри для асинхронних задач. Відмінність від `CyclicBarrier` та `CountDownLatch` полягає в більш гнучкому механізмі контролю над кількістю фаз і потоків у кожній фазі.

<p align="center">
  <img src="./phaser.gif" alt="CountDownLatch">
</p>

- [ ] Основні методи Phaser:

### `register()`:

- Реєструє новий потік (учасник) у цьому phaser.
### `arrive()`:

- Вказує, що потік (учасник) завершив поточну фазу, але він не буде чекати, поки інші потоки завершать.
arriveAndAwaitAdvance():

- Вказує, що потік (учасник) завершив поточну фазу і буде чекати, поки всі інші потоки також не завершать її.
### `arriveAndDeregister()`:

- Вказує, що потік (учасник) завершив поточну фазу і не братиме участі у наступних фазах.
### `getPhase()`:

- Повертає поточний номер фази.
### `bulkRegister(int parties)`:

- Реєструє задану кількість нових потоків (учасників) в цьому phaser.
### `getArrivedParties()`:

- Повертає кількість потоків, які завершили поточну фазу.
### `getUnarrivedParties()`:

- Повертає кількість потоків, які ще не завершили поточну фазу.
### `getRegisteredParties()`:

- Повертає загальну кількість потоків (учасників), зареєстрованих в phaser.
### `onAdvance(int phase, int registeredParties)`:

- Цей метод викликається, коли всі потоки завершили фазу. Зазвичай його перевизначають, щоб надати конкретну поведінку під час переходу до наступної фази.
- Phaser надзвичайно гнучкий і підтримує динамічне змінення кількості потоків, що беруть участь у фазах, та кількості фаз.