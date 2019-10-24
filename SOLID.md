### Single Responsibility Principle
A class or method should be responsible for doing only one thing and it should do that one thing really well. This helps clear the separation of responsibilities.
```
// Violates SRP. The invoice shouldn't be concerned about storing or printing.

public class Invoice {
	double calculateTotal() {
		// Calculate total value of items in this invoice.
	}
	void storeInvoiceDetails() {
		// Persist the invoice to a database.
	}
	void printInvoice() {
		// Print the invoice in a specific format.
	}
}
```
```
// Refactored

public class Invoice {
	public double calculateTotal() {
		// Calculate total value of items in this invoice.
	}
}

// Deals with printing invoices in whichever format our users want.
public interface InvoicePrinter {
	public void printInvoice(Invoice invoice);
}

// Deals with persisting invoices; this can known about database structure.
public interface InvoiceRepository {
	public void storeInvoice(Invoice invoice);
}
```

### Open/Closed Principle
Software should be open to extension, but closed to modification. We design our systems in such a way that we can easily add features without having to modify, recompile, and redeploy core components. This allows for changes to be isolated from shared, core components in the system, which reduces the risk of breaking changes.
```
// Violates Open/Closed. The account class needs to be modified if a new interest calculation is needed.

public class Account {
	private String accountNumber;
	private double balance;
	
	public double calculateInterest() {
		if (accountNumber.startsWith("000")) {
			// Savings account
			return balance * 0.05;
		} else if (accountNumber.startsWith("001")) {
			// Current account
			return balance * 0.01;	 
		} else {
			return 0;
		}
	}
}
```
```
// Refactored. A possible solution is to create different interfaces for different interest rates. Then create an interest calculation interface when we need to calculate the interest.

public class Account {
	// Fields and accessors omitted.
	public double calculateInterest(InterestCalculation interestCalculation) {
		return interestCalculation.calculateInterest(balance);
	}
}

public interface InterestCalculation {
	double calculateInterest(double balance);
}

public class SavingsInterestCalculation implements InterestCalculation {
	public double calculateInterest(double balance) {
		return balance * 0.05;
	}
}

public class CurrentInterestCalculation implements InterestCalculation {
	public double calculateInterest(double balance) {
		return balance * 0.01;
	}
}
```

### Liskov Substitution Principle
Various subtypes of a class should be able to be used interchangeably where an instance of that class is expected. Subtypes should retain the behavior of the main type. Children should be like their parents for what they inherit. Child class should be extending the behavior and not altering the behavior of the parent class. This allows us to easily swap out different implementations without affecting existing code.
```
// Violates LSP. We should be able to subsitute the child for the parent without any issues. The child class is now altering the behavior of the parent rather than extending it.

class Rectangle {
	public double height;
	public double width;
	
	public void setHeight(double value) {
		this.height = value;
	}
	
	public void setWidth(double value) {
		this.width = value;
	}
}

class Square extends Rectangle {
	// Height and width are equal in a square
	public void setHeight(double value) {
		this.height = value;
		this.width = value;
	}
	
	public void setWidth(double value) {
		this.width = value;
		this.height = value;
	}
}
```
```
// Refactored. A possible solution is creating a shape class. Both the rectangle and square classes can now be swapped with the shape class without any issue.

class Shape {
	public double height;
	public double width;
}

class Rectangle extends Shape {
	public void setHeight(double value) {
		this.height = value;
	}
	
	public void setWidth(double value) {
		this.width = value;
	}
}

class Square extends Shape {
	public void setHeight(double value) {
		this.height = value;
	}
	
	public void setWidth(double value) {
		this.width = value;
	}
}
```

### Interface Segregation Principle
Interfaces should be as small as possible and only expose those methods that are directly relevate to clients that use the interface. Consumers of a class should not be forced to depend on methods that they do not require. This displays a clear separation of responsibilities.
```
// Violates ISP. The ATM class has access to methods that can create customers and accounts. ATM should not be concerned with creating customers and accounts.

public class ATM {
	// Class that drives automated teller machines.
	private BankService bankService;
	
	public void makeDeposit(long accountNumber, double amount) {
		bankService.makeDeposit(accountNumber, amount);
	}
	
	public void makeWithdrawal(long accountNumber, double amount) {
		bankService.makeWithdrawal(accountNumber, amount);
	}
}

public interface BankService {
	public void makeDeposit(long accNumber, double amount);
	public void makeWithdrawal(long accNumber, double amount);
	public long openAccount(String custId, String accType);
	public long closeAccount(long accountNumber);
	public long createCustomer(String name, String address);
	public void disableCustomer(long customerId);
}
```
```
// Refactored. Now the ATM only has access to methods it cares about.

public class ATM {
	private TransactionService transactionService;

	public void makeDeposit(long accountNumber, double amount) {
		transactionService.makeDeposit(accountNumber, amount);
	}

	public void makeWithdrawal(long accountNumber, double amount) {
		transactionService.makeWithdrawal(accountNumber, amount);
	}
}

public interface TransactionService {
	public void makeDeposit(long accNumber, double amount);
	public void makeWithdrawal(long accNumber, double amount);
}

// Create interface to handle opening/closing account and then another interface to handle creating and disabling customers.
```

### Dependency Inversion Principle
High level objects should not depend on low level implementations. Abstractions should not depend on details and details should depend on abstractions. Depend on abstractions rather than concrete implementations. This helps reduce coupling between components by introducing abstractions (think of interfaces) between them. 
```
// Violates DIP. The ReportGenerator has a specific dependency on HtmlReportWrite class. This violates DIP if we want to generate a different report format.

public class HtmlReportWriter {
	public void writeReportToHtml(Report report) {
	// Generate HTML file containing report data.
	}
}

public class ReportGenerator {
	private HtmlReportWriter reportWriter = new HtmlReportWriter();
	public void generateReport(String reportName) {
		// Create and populate Report object.
		reportWriter.writeReportToHtml(report);
	}
}
```
```
// Refactored. The ReportGenerator now does not know or care about the format of the report. All it's doing is communicating with the ReportWriter interface.

public class ReportGenerator {
	private ReportWriter reportWriter;

	public void generateReport(String reportName) {
		// Create and populate Report object.
		reportWriter.writeReport(report);
	}

	public void setReportWriter(ReportWriter reportWriter) {
		this.reportWriter = reportWriter;
	}
}

public interface ReportWriter {
	void writeReport(Report report);
}

public class HtmlReportWriter implements ReportWriter {
	public void writeReport(Report report) {
		// Generate HTML file containing report data.
	}
}

public class CsvReportWriter implements ReportWriter {
	public void writeReport(Report report) {
		// Generate CSV file containing report data.
	}
}
```
