# Do *NOT* modify the existing build rules.
# You may add your own rules, e.g., "make run" or "make test".

LAB = kvdb
STUID = 161160037
STUNAME = 徐子恒

include Makefile.git

.PHONY: build submit

build: $(LAB).c
	$(call git_commit, "compile")
	gcc -fPIC -shared -std=gnu99 -O1 -Wall -o lib$(LAB).so $(LAB).c
	gcc -L./ -Wl,-rpath=./ -Wall -o a.out main.c -lkvdb

submit:
	cd .. && tar cj $(LAB) > submission.tar.bz2
	curl -F "task=M6" -F "id=$(STUID)" -F "name=$(STUNAME)" -F "submission=@../submission.tar.bz2" 114.212.81.90:5000/upload
