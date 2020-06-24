# M.plugin.XYLocator


Plugin que permite localizar las coordenas introducidas por el usuario en un Sistema de referencia determinado.
Las coordenadas son transformadas a proyección que tenga el mapa en ese momento.

![Imagen1](../img/xylocator1.png)

# Dependencias

- xylocator.ol.min.js
- xylocator.ol.min.css


```html
 <link href="../../plugins/xylocator/xylocator.ol.min.css" rel="stylesheet" />
 <script type="text/javascript" src="../../plugins/xylocator/xylocator.ol.min.js"></script>
```

# Parámetros

El constructor se inicializa con un JSON de options con los siguientes atributos:

- **position**. Indica la posición donde se mostrará el plugin
  - 'TL':top left (default)
  - 'TR':top right
  - 'BL':bottom left
  - 'BR':bottom right

- **zoom**. Indica el zoom que se hará cuando localice la coordenada, por defecto 16.

# Eventos

- **xylocator:locationCentered**
  - Evento que se dispara cuando se ha localizado la búsqueda del plugin sobre el mapa.
  - Expone, como parámetro devuelto, el **punto** actual calculado en la búsqueda

```javascript
mp.on('xylocator:locationCentered', (data) => {
   window.alert(`zoom: ${data.zoom}
   center: ${data.center[0].toFixed(2)}, ${data.center[1].toFixed(2)}`);
});
```

# Otros métodos


# Ejemplos de uso

```javascript
   const map = M.map({
     container: 'map'
   });

   const mp = new M.plugin.XYLocator({
        postition: 'TL',
      });

   map.addPlugin(mp);
```

```javascript
const mp = new XYLocator({
  position: 'TL',
  zoom: 16
});

map.addPlugin(mp);
```
