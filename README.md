# LaboratorioRoutingService
ROUTING
Los componentes creados toolbar tiene el ejemplo de como esta echo el routing.
Para crearlo primero tenemos crear el app-routing con el siguiente comando

myapp> ng g m app-routing --flat --module=app

se crea el archivo en la raíz de la carpeta app con el nombre app-routing.module.ts
y editamos este archivo de la siguiente manera.

1. Importamos RouterModule: import {RouterModule, Routes} from '@angular/router';
2. Importamos todos los componentes que hemos creado y que necesitemos rutear:
    import { NgModule } from '@angular/core';
    import { CommonModule } from '@angular/common';
    import {RouterModule, Routes} from '@angular/router';
    import {MycardsComponent} from './mycards/mycards.component';
    import {AcordionComponent} from './acordion/acordion.component';
    import {TableComponent} from './table/table.component';
    import {MyPortfolioComponent} from './my-portfolio/my-portfolio.component';
    import {MyformComponent} from './myform/myform.component'; 

3. Creamos la constante routes con nuestro array para cargar los componentes con su directorio:
  const  routes: Routes = [
  {path: 'mycards', component: MycardsComponent},
  {path: 'acordion', component: AcordionComponent},
  {path: 'table', component: TableComponent},
  {path: 'myportafolio', component: MyPortfolioComponent},
  {path: 'myform', component: MyformComponent},
  {path: '', redirectTo: '/mycards', pathMatch: 'full'}
  ];
4. Luego importamos el RouterModule
  @NgModule({
  declarations: [],
  imports: [
    CommonModule,
    RouterModule.forRoot(routes)
  ]
})

5. Luego editamos nuestro componente toolbar.html y el ts
  En el Toolbar.html se encuentran dos formas de como ejecutar el ruteo, la na mediante routerlink y la otra mediante un evento click
  que llama a un metodo que se encuentra en el toolbar.ts y mediante una sentencia if este permite ejecutar el redireccionamiento por medio del router importado a esta clase.

SERVICE
Se crea un servcio mediante el comando
myapp> ng g s /servicios/personal

se crea una carpeta servicios y ella el archivo personal.ts la misma que contine un array de tipo personal con nombres, apellidos, cargo, email
este es llamado para ser consumido por el componente table.html, table.ts.

