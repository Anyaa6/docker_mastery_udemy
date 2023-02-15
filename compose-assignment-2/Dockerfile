FROM drupal:9.3.13

RUN apt-get update && apt-get install -y git \
	&& rm -rf /var/lib/apt/lists/*

WORKDIR /var/www/html/themes

RUN git clone --branch 8.x-4.x --single-branch --depth 1 https://git.drupalcode.org/project/bootstrap.git \
	# This drupal container runs as www-data user but the build actually runs as root,
	# so often we have to do things like `chown` to change file owners to the proper user:
	&& chown -R www-data:www-data bootstrap

WORKDIR /var/www/html
