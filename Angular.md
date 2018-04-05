## Angular

------

[TOC]

------

### Node.js

------

##### Intro

Est basé sur V8. C'est une plateforme open source pour développer des applications côté serveur en utilisant javascript. (= machine virtuelle de javascript = javascript côté serveur).



Install : 

1. Node.js
2. Typescript -g
3. @angular/cli -g

------

##### Callback (=fonction)

```javascript
var callback = function(error, response, body)
{
    console.log("file uploaded with success");
}

request('http://monsite.com/file.zip', callback);
request('http://monsite.com/otherfile.zip', callback);
```

------

##### NPM

Npm est un moyen de réutiliser du code déjà écrit (+-= à Maven). Facilite également la mise à jour du code (via versioning). 

```bash
#céer nouvelle application
npm init 

#Avoir les dépendances sue le paquet ajouté
npm install <package name> --save

#installation ou maj de tous les packages de package.json
npm install

#désinstaller package
npm uninstall <package name>
```

------

### TypeScript

Possibilité d'utiliser des classes, des *extends*, getters, setters, static

##### Attribut ?

```javascript
var thing:
{
    name : string;
    //ici l'attribut nickname n'est pas obligatoire à l'appel de la methode
    nickname? : string;
}
```

------

##### Décorateurs

Permet d'ajouter des métadonnées

```typescript
@Injectable()
export class DataService()
{
    data = [1,2,3];
}
```



------

### Angular

![angularBigpicture](/Users/Berenger/Documents/GitKraken/GKCheatSheet/images/angularBigpicture.png)

Lancer le serveur : 

```Bash
ng serve
```



------

##### Component

Nouveau composant : 

```JavaScript
@Component
({
        //metadatas
    selector : "app-comp"
})

export class appComponent{};
```

Appel au composant dans HTML :

```html
<app-comp> </app-comp>
```

Convention de nommage:

- Fichier : *<component name>*.component.ts
- Classe: *<componentName>*.Component

------

##### Binding

```nginx
/*NOM | REPRESENTATION
.ts
.html*/

/*//interpolation | {{expression}}*/
name : string;
{{name}}

/*propriete/attribut/style/classe | [property] = "expression"*/
imageUrl : string = "nom_de_l_image.png";
<img [attr.src] = "imageUrl" />

/*evenement | (event) = "statement"*/
save(){console.log("saved")};
<button (click)="save()"> Save </button>

/*event | $event*/
changeIt(m){this.movie=m};
<input (input)=changeIt($event.target.value) >

/*bidirectionnel | [(ngModel)] = "property"*/
movie="king kong";
<input [(ngModel)] = "movie" /><p>{{movie}}</p>
```

------

##### Modules

*ngFor

```Html
<li *ngFor='let m of movies'>
    {{m}}
 </li>
```

```typescript
movies: string[] = ["Watchmen", "300", "Sucker Punch", "Man of steel"];
```

*ngIf

```Html
<p *ngIf="nb<nbGold">Too small</p>
```

Operateur |

```typescript
name : string = "Bonjour"
```

```html
<p> Hello {{name | uppercase}} </p>
```

------

##### Injection de dépendances :

- Façon d'erregister une dapendace
- Façon de déclarer quelles dépendances sont requises

Injectable : 

```typescript
@Injectable
export class RaceService
{
    constructor(private _http : Http) {}
    list()
    {
        return this._http.get("http://localhost:9000/races").map(res => ers.json());
    }
}
```



Récupérer l'injection :

```typescript
@Component
({
    selector: 'race-cmp',
    providers: [provide(raceService, {useClass: fakeRaceService})],
    template: `<strong>Race list</strong>`
})

export class RacesCmp
{
    constructor(private _raceService: RaceService){}
    
    list()
    {
        return this._raceService.list();
    }
}
```

------

##### Programation réactive

Libraires : *RxJava*, *<u>RxJS</u>* pour respectivement Java et JavaScript. 

- S'abonner à un flux
- Définir un listener