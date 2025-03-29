In **select-microservices.md** already we have done locally

Now, remove dockerfile which is already existing and start create new one

-'''rm -rf Dockerfile```

To check if it is deleted or not

-``` git status'''

Now start create a dockerfile 

''' FROM golang:1.24 AS builder

WORKDIR /app

COPY . .

RUN go mod download

RUN go build -o /app/product-catalog .

FROM alpine AS release

WORKDIR /app

COPY --from=builder /app/product-catalog /app/

COPY ./products/ /app/products

RUN chmod +x /app/product-catalog

ENV PRODUCT_CATALOG_PORT=8080

EXPOSE ${PRODUCT_CATALOG_PORT}

ENTRYPOINT ["/app/product-catalog"]```


