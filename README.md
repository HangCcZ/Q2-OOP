# Q2-OOP

```
class Human {
  mouthStatus = 'close';

  constructor(name, title) {
    this.name = name;
    this.title = title;
  }

  getTitle() {
    return this.title;
  }

  getMouthStatus() {
    return this.mouthStatus;
  }

  setMouthOpen(requester) {
    if (requester === this || requester.getTitle() === 'Doctor') {
      this.mouthStatus = 'Open';
      return 'My mouth is open';
    } else {
      return 'You are not my doctor';
    }
  }

  setMouthClose(requester) {
    if (requester === this || requester.getTitle() === 'Doctor') {
      this.mouthStatus = 'Close';
      return 'My mouth is closed';
    } else {
      return 'You are not my doctor';
    }
  }
}

let samSmith = new Human('Sam Smith', 'Doctor'); // Doctor
let brianPark = new Human('Brian Park', 'Patient'); // Patient
let joeKim = new Human('Joe Kim', 'Receptionist'); // Non-Doctor

//Doctor Asking
console.log(brianPark.setMouthOpen(samSmith)); // My mouth is open
console.log(brianPark.getMouthStatus()); // Open
console.log(brianPark.setMouthClose(samSmith)); // My mouth is closed
console.log(brianPark.getMouthStatus()); // Close

// Non-Doctor Asking
console.log(brianPark.setMouthOpen(joeKim)); // You are not my doctor
console.log(brianPark.getMouthStatus()); // Close
console.log(brianPark.setMouthClose(joeKim)); // You are not my doctor
console.log(brianPark.getMouthStatus()); // Close

// Self-Asking
console.log(brianPark.setMouthOpen(brianPark)); // My mouth is open
console.log(brianPark.getMouthStatus()); // Open
console.log(brianPark.setMouthClose(brianPark)); // My mouth is closed
console.log(brianPark.getMouthStatus()); // Close
```
