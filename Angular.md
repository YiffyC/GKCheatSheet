## Angular

------

[TOC]

------

### Node.js

------

##### Intro

Est basé sur V8. C'est une plateforme open source pour développer des applications côté serveur en utilisant javascript. (= machine virtuelle de javascript = javascript côté serveur).

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

Attribut ?

```javascript
var thing:
{
    name : string;
    //ici l'attribut nickname n'est pas obligatoire à l'appel de la methode
    nickname? : string;
}
```

------

Décorateurs

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

