# 6 - Recap



* Para modelar relaciones entre data podemos hacer referencia a un documento embebido o a otro documento.
* Al hacer referencias a documentos no hay relacion real entre ellos asi que cuidado de que existan realmente
* 




* * Referencing documents \(normalization\) is a good approach when you want to

  enforc~~e~~ data consistency. Because there will be a single instance of an object in

  the database. But this approach has a negative impact on the performance of

  your queries because in MongoDB we cannot JOIN documents as we do in

  relational databases. So, to get a complete representation of a document with its

  related documents, we need to send multiple queries to the database.

* Embedding documents \(denormalization\) solves this issue. We can read a

  complete representation of a document with a single query. All the necessary

  data is embedded in one document and its children. But this also means we’ll

  have multiple copies of data in different places. While storage is not an issue

  these days, having multiple copies means changes made to the original

  document may not propagate to all copies. If the database server dies during an

  update, some documents will be inconsistent. For every business, for every

  problem, you need to ask this question: “can we tolerate data being inconsistent

  for a short period of time?” If not, you’ll have to use references. But again, this

  means that your queries will be slower.

