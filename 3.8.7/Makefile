.PHONY: image release

image:
	docker buildx build . \
		--platform linux/arm64,linux/amd64,linux/amd64/v2 \
		-t thesheepishlions/jekyll-s3:3.8.7

release:
	docker push thesheepishlions/jekyll-s3:3.8.7
