---

# Parte 1 – Granular Error Handling

## Descripción

En esta parte se implementó un manejo de errores tipado para CameraX, permitiendo distinguir claramente entre distintos tipos de fallos durante la captura de fotos.

Se creó una `sealed class CaptureError` con múltiples tipos de error específicos.

Los errores de `ImageCaptureException` fueron mapeados correctamente a esta sealed class, y el `Repository` fue actualizado para incluir un nuevo caso `PhotoCaptureFailed` dentro de `CreateSpotResult`.

La UI ahora muestra mensajes específicos dependiendo del tipo de error, evitando mensajes genéricos.

---

## Video explicación

Link:  


---

## ✅ Definition of Done (DoD)

- [x] Sealed class exists – `CaptureError` sealed class with 3+ error types  
- [x] Errors are mapped – `ImageCaptureException.imageCaptureError` codes mapped to sealed class  
- [x] Repository updated – `CreateSpotResult` has new `PhotoCaptureFailed` case  
- [x] UI shows specific messages – Each error type displays a different user-friendly message  
- [x] No crashes – App handles all error cases gracefully
      
---

# Parte 2 – Spot Deletion Feature

## Descripción

En esta parte se implementó la funcionalidad completa de eliminación de Spots desde el mapa.

Se agregó el método `deleteSpot(id: Long)` en `SpotDao`, y el `Repository` ahora coordina tanto la eliminación en la base de datos como la eliminación del archivo de imagen asociado en `filesDir`.

La eliminación se activa mediante un long-press sobre la ventana de informacion del marcador, mostrando un `AlertDialog` de confirmación antes de eliminarlo.

---

## Video explicación

Link:  


---

## ✅ Definition of Done (DoD)

- [x] DAO method exists – `deleteSpot(id: Long)` query in `SpotDao`  
- [x] Repository coordinates – Deletes from DB AND deletes photo file  
- [x] Long-press triggers dialog – Marker info window responds to long-press  
- [x] Confirmation dialog – `AlertDialog` asks "Are you sure?" before deletion  
- [x] File cleanup – Photo file is deleted from `filesDir`  
- [x] UI updates automatically – Map removes marker after deletion (Flow reactivity)  
- [x] Edge cases handled – Graceful handling if file doesn't exist  
