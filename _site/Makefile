JEKYLL_VERSION := 3.5

all:

define run_jekyll
	docker run --rm --volume="$$PWD:/srv/jekyll" -it jekyll/jekyll:$(JEKYLL_VERSION) $1
endef
define run_jekyll2
	docker run --rm --volume="$$PWD:/srv/jekyll" \
	-it $1 jekyll/jekyll:$(JEKYLL_VERSION) -- $2
endef

# init-jekyll:
# 	$(call run_jekyll, jekyll new .)

build:
	$(call run_jekyll, jekyll build)
watch:
	$(call run_jekyll, jekyll build --watch)

# docker run --name newblog --volume="$PWD:/srv/jekyll" 
# 	-p 3000:4000 -it jekyll/jekyll:$JEKYLL_VERSION 
# 	jekyll serve --watch --drafts

run:
	docker run --rm --volume="${PWD}:/srv/jekyll" \
	-p 4000:4000 -it \
	jekyll/jekyll:$(JEKYLL_VERSION)  \
	jekyll serve --force_polling --drafts

# serve:
# 	docker run --name newblog --volume="$$PWD:/srv/jekyll" -p 3000:4000 -it jekyll/jekyll:$(JEKYLL_VERSION) jekyll serve --watch --drafts

# devbox-serve:
# 	devbox shell -- jekyll serve --watch --drafts
