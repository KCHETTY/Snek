CLANG =	clang++

NAME = sfml.so

CFLAGS = -Wall -Werror -Wextra

C++_TYPE = -std=c++11

SFML_lIBS = -L ~/.brew/Cellar/sfml/2.4.2/lib/ -lsfml-graphics -lsfml-window -lsfml-system

SFML_CFLAGS = -I ~/.brew/Cellar/sfml/2.4.2/include/

HEADER = sfml.hpp

SRC_PATH = ../Src/

SRC = $(SRC_PATH)libs.cpp sfml.cpp

OBJ = $(SRC:.cpp=.o)

%.o: %.cpp
	$(CLANG) -c $(C++_TYPE) $(CFLAGS) $(SFML_CFLAGS) -fpic $< -o $@

all: $(NAME)

$(NAME): $(OBJ) $(HEADER)
	$(CLANG) $(CFLAGS) $(SFML_lIBS) -fPIC -shared -Qunused-arguments -o $(NAME) $(OBJ)

sfml:
	brew install sfml

clean:
	rm -rf $(OBJ)

fclean: clean
	rm -rf $(NAME)

re: fclean all
