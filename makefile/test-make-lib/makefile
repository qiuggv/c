CC=gcc

INSTDIR=/home/qiuxy/

MYLIB=mylib.a

myapp: main.o $(MYLIB)
	${CC} -o myapp main.o $(MYLIB)

#将2.o和3.o打包成mylib.a
$(MYLIB): $(MYLIB)(2.o) $(MYLIB)(3.o)
main.o: main.c a.h
2.o: 2.c a.h b.h
3.o: 3.c b.h c.h

clean:
	-rm main.o 2.o 3.o $(MYLIB)
#减号的作用，是让make忽略rm命令的执行结果

install: myapp
	@if [ -d $(INSTDIR) ]; \
	then \
	cp myapp $(INSTDIR);\
	chmod a+x $(INSTDIR)/myapp; \
	chmod og-w $(INSTDIR)/myapp; \
	echo "Installed in $(INSTDIR)"; \
	else \
	  echo "Sorry, $(INSTDIR) does not exist"; \
	fi
#由于make执行规则的时候，调用一个shell，所以必须都放在同一行
#以符号@开头，表示make在执行这些规则之前，不会在标准输出上显示命令本身
