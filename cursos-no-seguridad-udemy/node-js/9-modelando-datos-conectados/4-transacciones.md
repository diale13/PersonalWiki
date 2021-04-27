# 4 - Transacciones

{% embed url="https://docs.mongodb.com/manual/core/transactions/" %}

Usa un modulo de npm llamado **FAWN.** Ademas del require utiliza un init\(mongoose\)

![](../../../.gitbook/assets/imagen%20%28588%29.png)

```javascript
try {
await new Fawn.Task()
.save(‘rentals’, newRental)
.update(‘movies’, { _id: movie._id }, { $inc: numberInStock: -1 }})
.run();
}
catch (ex) {
// At this point, all operations are automatically rolled back
```

La gracia del fawn es que si algo falla en la mitad se pueda hacer un rollback

![](../../../.gitbook/assets/imagen%20%28589%29.png)

