.PHONY: postgres adminer migrate

postgres:
	docker run -d --rm --name postgres -p 127.0.0.1:5432:5432 -e POSTGRES_PASSWORD=postgres -e POSTGRES_HOST_AUTH_METHOD=trust -e POSTGRES_USER=user postgres

adminer:
	docker run --rm -ti -p 127.0.0.1:8080:8080 adminer

migrate:
	migrate -source file://migrations -database postgres://postgres:secret@localhost/postgres?sslmode=disable up