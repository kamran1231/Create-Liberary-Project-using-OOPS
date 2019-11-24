# Create-Liberary-Project-using-OOPS


class Liberary:

    def __init__(self,book_list,liberary_name):
        self.book_list = book_list
        self.liberary_name = liberary_name
        self.lend_book = {}


    def display_book(self):
        print(self.book_list)


    def add_book(self):
        book = input('Enter the Book name: ')
        self.book_list.append(book)


    def lend_books(self):
        book = input('Enter the Book name: ')
        if book not in self.book_list:
            print('you enter wrong book name')
        if book in self.book_list:
            name = input('enter your name: ')
            self.book_list.remove(book)
            self.lend_book[book] = name

        else:
            if self.lend_book.get(book):
                print(f"Book does not exist in library this book taken by {self.lend_book[book]}")


    def return_book(self):
        book = input('Enter your return book name: ')
        if book in self.lend_book:
            self.book_list.append(book)
            del self.lend_book[book]

        else:
            print('Please enter valid book name: ')



    # def add_book(self):
    #     Liberary.listlib.append(self)

if __name__ == '__main__':
    book_list = ['c++','java','python']
    kamran_liberary = Liberary(book_list,'kamran_liberary')

    while True:
        print("WELCOME TO MY LIBERARY")
        print(' 1. ADD BOOK: \n 2. LEND BOOK: \n 3. RETURN BOOK: \n 4. DISPLAY ALL BOOK:')

        choice = input('Enter your choice: ')
        if choice == '1': # ADD BOOK

            kamran_liberary.add_book()
            print('Book is added Successfully')

        elif choice == '2':
            kamran_liberary.lend_books()
            print('Book is lended successfully')

        elif choice == '3':
            kamran_liberary.return_book()
            print('Book is return successfully')


        elif choice == '4':
            kamran_liberary.display_book()
