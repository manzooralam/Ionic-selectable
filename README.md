# Ionic-selectable

(see more)[https://www.npmjs.com/package/ionic-selectable]
An Ionic component similar to Ionic Select, that allows to search items, including async search, infinite scrolling and more.

## Step 1:

// In Ionic 4
` npm install ionic-selectable@4.4.0 --save `

## Step 2:
import IonicSelectableModule to your app.module.ts that is normally located in src\app\app.module.ts.

`` imports: [
    IonicSelectableModule
  ]
  ``
  
  ## Step 3:
  
  Additionally, if you use Ionic 3+ you might be as well using lazy loaded pages. Check if your pages have a module file, for example, home.module.ts, and if they do then import IonicSelectableModule to each page module too.
  
  ``
  imports: [
    IonicPageModule.forChild(HomePage),
    IonicSelectableModule
  ]
  ``
  
  ## Step 4:
  
  Add it to template.
  
  
  ``
  <ion-item>
  <ion-label>Port</ion-label>
  <ionic-selectable
    item-content // Required for Ionic 3 only.
    [(ngModel)]="port"
    [items]="ports"
    itemValueField="id"
    itemTextField="name"
    [canSearch]="true"
    ` (onChange)="portChange($event)"> `
  </ionic-selectable>
</ion-item>
``


## Step 5:
Configure it.

``
import { IonicSelectableComponent } from 'ionic-selectable';

class Port {
  public id: number;
  public name: string;
}

@Component({ ... })
export class HomePage {
  ports: Port[];
  port: Port;

  constructor() {
    this.ports = [
      { id: 1, name: 'Tokai' },
      { id: 2, name: 'Vladivostok' },
      { id: 3, name: 'Navlakhi' }
    ];
  }

  portChange(event: {
    component: IonicSelectableComponent,
    value: any 
  }) {
    console.log('port:', event.value);
  }
}

``

(Refference)[https://www.npmjs.com/package/ionic-selectable]
