postgres:
	docker run --name postgres-alpine -p 5432:5432 -e POSTGRES_USER=root -e POSTGRES_PASSWORD=azerty -d postgres:alpine
createdb:
	docker exec -it postgres-alpine createdb --username=root --owner=root simple_bank
dropdb:
	docker exec -it postgres-alpine dropdb simple_bank
migrateup:
	migrate -path migration -database "postgres://root:azerty@localhost:5432/simple_bank?sslmode=disable" -verbose up
migratedown:
	migrate -path migration -database "postgres://root:azerty@localhost:5432/simple_bank?sslmode=disable" -verbose down

.PHONY: postgres createdb dropdb migrateup migratedown