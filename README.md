# AngularSolidPrinciple


# What is SOLID principle in Angular

SOLID is a set of design principles that can be used to develop maintainable and scalable software applications. It stands for Single Responsibility Principle (SRP), Open-Closed Principle (OCP), Liskov Substitution Principle (LSP), Interface Segregation Principle (ISP), and Dependency Inversion Principle (DIP). Angular is a popular open-source framework for building web applications, and it can be used to implement SOLID design patterns.

# 1. S - Single Responsibility Principle (SRP):

The SRP states that a class should have only one reason to change. In Angular, this can be implemented by creating small, focused components that do one thing well. For example, a component that displays a list of items should only be responsible for displaying the list, and not for fetching the data or updating the items.


@Component({
  selector: 'app-item-list',
  templateUrl: './item-list.component.html',
})
export class ItemListComponent {
  @Input() items: Item[];

  constructor() { }
}

# 2. Open/Closed Principle (OCP):

The OCP states that a class should be open for extension but closed for modification. In Angular, this can be implemented by using interfaces and abstract classes to define behavior, and then implementing those interfaces or extending those classes in concrete classes. For example, if we have a service that fetches data from a backend API, we can define an interface for the service and then create concrete implementations of that interface for each backend API we need to support.

interface DataService {
  getData(): Observable<any>;
}

@Injectable({
  providedIn: 'root'
})
export class ApiService implements DataService {
  constructor(private http: HttpClient) {}

  getData(): Observable<any> {
    return this.http.get('/api/data');
  }
}


# 3. Liskov Substitution Principle (LSP):

The LSP states that objects of a superclass should be replaceable with objects of a subclass without affecting the correctness of the program. In Angular, this can be implemented by using inheritance to create subclasses that inherit behavior and properties from a superclass. For example, if we have a base component that displays a list of items, we can create a child component that extends the base component and adds additional behavior or styling.

@Component({
  selector: 'app-item-list',
  templateUrl: './item-list.component.html',
})
export class ItemListComponent {
  @Input() items: Item[];

  constructor() { }
}

@Component({
  selector: 'app-special-item-list',
  templateUrl: './special-item-list.component.html',
})
export class SpecialItemListComponent extends ItemListComponent {
  constructor() {
    super();
  }

  getSpecialItems(): Item[] {
    // implementation details
  }
}

# 4. Interface Segregation Principle (ISP):

The ISP states that a class should not be forced to depend on methods it does not use. In Angular, this can be implemented by creating small, focused interfaces that define behavior for a specific use case. For example, if we have a service that manages user authentication, we can create separate interfaces for login, logout, and user information retrieval.

interface LoginService {
  login(username: string, password: string): Observable<boolean>;
}

interface LogoutService {
  logout(): Observable<boolean>;
}

interface UserService {
  getUserInfo(): Observable<User>;
}

@Injectable({
  providedIn: 'root'
})
export class AuthService implements LoginService, LogoutService, UserService {
  // implementation details
}

# 5. Dependency Inversion Principle (DIP):

The DIP states that high-level modules should not depend on low-level modules, but should depend on abstractions. In Angular, this can be implemented by using dependency injection to provide dependencies to a class or component. For example, if we have a component that needs to make HTTP requests, we can inject an HTTP service into that component instead of creating a new instance of the service inside the component.

@Component({
  selector: 'app-item-list',
  templateUrl: './item-list.component.html',
})
export class ItemListComponent {
  items: Item[];

  constructor(private http: HttpClient) { }

  ngOnInit() {
    this.http.get('/api/items').subscribe((response) => {
      this.items = response;
    });
  }
}
