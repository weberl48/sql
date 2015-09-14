# SQL Join statements

![SQL join venn diagram](http://i.stack.imgur.com/UI25E.jpg)


full-outer-A-full-B-full

SELECT motorcycles.name AS vehicle, drivers.name AS drive FROM motorcycles FULL OUTER JOIN drivers ON motorcycles.id = drivers.motorcycle_id

full-outer-A-partial-B-partial

SELECT motorcycles.name AS vehicle, drivers.name AS driver FROM motorcycles FULL OUTER JOIN drivers ON motorcycles.id = drivers.motorcycle_id WHERE motorcycles.id id NULL or drivers.motorcycle_id IS NULL;

inner-A-partial-B-partial

SELECT motorcycles.name AS vehicle, drivers.name AS driver FROM motorcycles INNER JOIN drivers ON motorcycles.id = drivers.motorcycle_id;

left-A-full-B-partial

SELECT motorcycles.name AS vehicle, drivers.name AS driver FROM motorcycles LEFT JOIN drivers ON drivers.motorcycle_id = motorcycles.id;

left-A-partial-B-NULL

SELECT motorcycles.name AS vehicle, drivers.name AS driver FROM motorcycles LEFT JOIN drivers ON drivers.motorcycle_id IS NULL;

right-A-null-B-partial

SELECT motorcycles.name AS vehicle, drivers.name FROM motorcycles RIGHT JOIN drivers ON drivers.motorcycle_id = motorcycles.id WHERE motorcycles.id IS NULL

right-A-partial-B-full

SELECT motorcycles.name AS vehicle, drivers.name AS driver FROM motorcycles RIGHT JOIN drivers ON drivers.motorcycle_id = motorcycles.id
