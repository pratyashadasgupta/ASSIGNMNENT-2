# ASSIGNMNENT-2

EMPLOYEE CLASS

package com.junit.empoyee;

import com.example.employee.factory.EmployeeValidationException;

public class Employee {
	
	String Name;
	String Role;
	long Salary;
	
	public Employee()
	{
		
	}
	
	public Employee(String Role) {
		 this.Role= Role;
	}
	
	public String toString() {
		
		return "Role: "+Role;
		
	}
	
	public String specialcharvalidation(String Name) throws EmployeeValidationException {
		
		for(int i=0; i<Name.length();i++) {
			if (Name.charAt(i)=='@'|| Name.charAt(i)=='$'|| Name.charAt(i)=='!'|| Name.charAt(i)=='#'||Name.charAt(i)=='%') {
				
				    throw new EmployeeValidationException();
			    
			}
		}
		
		return Name+" does not have special characters";
		
	
	}
}

HR CLASS
package com.junit.empoyee;


public class HR extends Employee {

	public HR(String Role) {
		super(Role);
		
		// TODO Auto-generated constructor stub
	}
}

MANAGER CLASS
package com.junit.empoyee;


public class Manager extends Employee {

	public Manager(String Role) {
		super(Role);
		
		// TODO Auto-generated constructor stub
	}
}


EMPLOYEE FACTORY
package com.example.employee.factory;


import static org.junit.Assert.assertEquals;
import static org.junit.Assert.assertThat;
import static org.junit.Assert.assertThrows;

import org.hamcrest.core.IsInstanceOf;
import org.junit.jupiter.api.Test;

import com.junit.empoyee.Employee;
import com.junit.empoyee.EmployeeService;
import com.junit.empoyee.HR;
import com.junit.empoyee.Manager;


public class EmployeeFactory {
	  public static Employee createEmployee(String Role) {
	       switch(Role) {
	       case "HR" : return new HR(Role);
	       case "Manager" : return new Manager(Role);
		   }
		
		      return null;
	  }
	
	    @Test
	    public void specialcharvalidationTest() throws EmployeeValidationException {
	    	 Employee employee = new Employee("HR");
		     assertEquals( "Rajesh does not have special characters", employee.specialcharvalidation("Rajesh"));
		     assertThrows(EmployeeValidationException.class, () -> employee.specialcharvalidation("R@jesh"));
		     assertThat(employee, IsInstanceOf.instanceOf(Employee.class));

	    }
	    
	    
	    public static void main(String[] args) throws EmployeeValidationException {
	    
	    	Employee e3 = new Employee();
	    	EmployeeService e4= new EmployeeService();
	    	e4.calculateSalary(e3, 0.1);
	    	
	  }
	 }
	 

EMPLOYEE SERVICE

package com.junit.empoyee;

public class EmployeeService {
	
	Employee emp = new Employee();
	
	public void calculateSalary(Employee emp , double d) {
		emp.Salary = (long) (emp.Salary + emp.Salary *d);
		System.out.println(emp.Salary);
	}
	
}

package com.example.employee.factory;

public class EmployeeValidationException extends Exception {

}
