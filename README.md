# JavaAdressbook

//this is a blue print to create an adress book (like every class is a blueprint)
public class ArrayAdressBook {
	
	// Person is a data type, persons is a attribute
	int nextFreeSpace = 0;
	Person[] persons;

	// empty Konstruktor, first methode:
	ArrayAdressBook(int groesse) {//groesse means number
		if (groesse < 1) {
			groesse = 1;
		}
		this.persons = new Person[groesse];//Don't understand syntax

	}

	// more methodes:
	public void addPerson(Person human) {  //methode accepts a referese on a "Person-Object" as a parameter. We call this person object human
		if (persons.length == nextFreeSpace) {
			//hier Methode aufrufen, die das Array kopiert
			this.copyArray();
		}
		
		persons[nextFreeSpace] = human;
		nextFreeSpace = nextFreeSpace + 1;

	}
	//Methode,which copies the small array into the big array
	private void copyArray() {
		Person[] bigArray = new Person [2*persons.length];
		for (int i = 0; i < persons.length; i++) {
			bigArray[i] = persons[i];	
		}
		this.persons = bigArray;
	}

	// Here isert print() methode, which indicates, how many spaces in the address book are free and how many are taken
	public void print() {
		System.out.println(this.nextFreeSpace + "places are currently occupied");	
		System.out.println("capacity " + this.persons.length);
	
 } One thing is still missing here

 ------------------------------------------------------
public class Person {

	// This is my blueprint for creating a new person-Object
	String name;
	int birthday;
	
	Person(String name, int birthday) {
		this.name = name;
		this.birthday = birthday;		
	}
	
	void print() {
		System.out.println("Name: " + this.name);
		System.out.println("Geburtsdatum; " + this.birthday);
	}
	
	boolean isBirthday(int date) {
		return birthday % 10000 == date % 10000;
		//Modulo Operator liefert die letzten 4 Stellen. Es wird also im Jahrgang nach dem Monat und Tag gesucht
	}

}

 
}
