route.js, подключение
```
  import AdditionalModel from 'media-rights/utils/classes/routes/additional-model';
```


route.js, регистрация используемых дполнительных моделей
```
additionalModel: computed(function () {
  let controller = this.currentController;

  return [
    AdditionalModel.create({
      loadOnStartup: true,
      controllerPropertyName: `reports`,
      promise: (params) => {
        return this.store.query(`klf-rep-title`, params);
      },
      onSuccess: (result, currentController, queryParams) => {

      },
      onFailure: (response, currentController, queryParams) => {
        
      },
    }),
  ];
}),
```



route.js, обновление _указанной_ модели
```
this.send("reloadAdditionalModel", "model.ideDatFileCells", {
idFile: this.get('model.importFile.id')
});
```

controller.js, обновление _указанной_ модели
```
this.send("reloadAdditionalModel", "model.ideDatFileCells", {
idFile: this.get('model.importFile.id')
});
```
