
> [!IMPORTANT] Saving Data
> MongoDB stores documents in colletions.


> [!IMPORTANT] Collections
> Are analogous to tables in relational databases. -> If a collection does not exist, MongoDB creates the collection when you first store data for that collection.


> [!WARNING] Restriction on Collection Names
> Collection names should begin with an underscore or a letter character, and cannot:
> - contain the `$`.
> - Be an empty string.
> - Contain the null character.
> - Begin with the `system.` prefix(Reserved for internal use).
> - Contain `.system.`.



> [!WARNING] Inserting documents in collections
- `db.collection.insertMany()` -> Returns a documents that contains the acknowledgement indicator and an array that contains the `_id` of each successfully inserted documents.
	```
	{
	  acknowledged: true,
	  insertedIds: {
	    '0': ObjectId('673c8545e32e96b478838726'),
	    '1': ObjectId('673c8545e32e96b478838727'),
	    '2': ObjectId('673c8545e32e96b478838728'),
	    '3': ObjectId('673c8545e32e96b478838729')
	  }
	}
	```


> [!WARNING] Find Documents
> 
```
db.collection.find({})

```

> [!WARNING] Delete a Document
```
db.collection.deleteOne()
```
