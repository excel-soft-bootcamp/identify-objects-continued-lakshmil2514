# Injectors

- Injectors are data structures that store instructions detailing where and how services form. 
- They act as intermediaries within the Angular DI system.
- Module, directive, and component classes contain metadata specific to injectors.
- A new injector instance accompanies every one of these classes. 
- The providers: [] metadata accepts services that then register with the class’ injector.
- This provider field adds the instructions necessary for an injector to function. 
  
// service

import { Injectable } from '@angular/core';

@Injectable({
  providedIn: /* injector goes here */
})
export class TemplateService {
  constructor() { }
}

// module

import { NgModule } from '@angular/core';
import { CommonModule } from '@angular/common';

@NgModule({
  imports: [
    CommonModule
  ],
  declarations: [],
  providers: [ /* services go here */ ]
})
export class TemplateModule { }

// directive

import { Directive } from '@angular/core';

@Directive({
  selector: '[appTemplate]',
  providers: [ /* services go here */ ]
})
export class TemplateDirective {
  constructor() { }
}

//component

import { Component } from '@angular/core';

@Component({
  selector: 'app-template',
  templateUrl: './template.component.html',
  styleUrls: ['./template.component.css'],
  providers: [ /* services go here */ ]
})
export class TemplateComponent {
  // class logic ...
}

