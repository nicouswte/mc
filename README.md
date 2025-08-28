# mc

    class User:
    def __init__(self, user_id, name, email):
        self.user_id = user_id
        self.name = name
        self.email = email

    def __repr__(self):
        return f"User({self.user_id}, {self.name}, {self.email})"


    class Product:
    def __init__(self, product_id, name, price):
        self.product_id = product_id
        self.name = name
        self.price = price

    def __repr__(self):
        return f"Product({self.product_id}, {self.name}, R${self.price:.2f})"



    class UserController:
    def __init__(self):
        self.users = []

    def create_user(self, user_id, name, email):
        user = User(user_id, name, email)
        self.users.append(user)
        return user

    def list_users(self):
        return self.users


    class ProductController:
    def __init__(self):
        self.products = []

    def add_product(self, product_id, name, price):
        product = Product(product_id, name, price)
        self.products.append(product)
        return product

    def list_products(self):
        return self.products

    if __name__ == "__main__":
    user_controller = UserController()
    product_controller = ProductController()

 
    user_controller.create_user(1, "Alice", "alice@email.com")
    user_controller.create_user(2, "Bob", "bob@email.com")

    product_controller.add_product(1, "Notebook", 3500.00)
    product_controller.add_product(2, "Mouse", 120.00)

    print("Usuários cadastrados:")
    print(user_controller.list_users())

    print("\nProdutos cadastrados:")
    print(product_controller.list_products())
