---
title: Usar la autenticación en dos fases con el cliente de Skype empresarial y Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: 'Resumen: Use la autenticación en dos fases con Skype empresarial Server y Skype empresarial.'
ms.openlocfilehash: 532e7567444b78dd30d053cf91aef1c10f0970bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286112"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a>Usar la autenticación en dos fases con el cliente de Skype empresarial y Skype empresarial Server
 
**Resumen:** Use la autenticación en dos fases con Skype empresarial Server y Skype empresarial.
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Iniciar sesión en Skype Empresarial por primera vez

La información de inicio de sesión se suele configurar automáticamente cuando Skype empresarial está instalado. Pero la primera vez que use Skype empresarial, es posible que tenga que iniciar el cliente de forma manual.
  
### <a name="to-sign-in-for-the-first-time"></a>Iniciar sesión por primera vez

1. Inicie sesión en la red de su organización.
    
2. Seleccione **iniciar** > **todos los programas** > **Skype empresarial**.
    
    Aparecerá la pantalla de inicio de sesión.
    
    - Si el cuadro de dirección para inicio de sesión ya está rellenado, confirme que la dirección que aparece es correcta.
    
    - Si no es correcta, o si el cuadro está vacío, escriba su dirección de inicio de sesión (normalmente es la misma que su dirección de correo electrónico).
    
    - Si aparece un cuadro de contraseña vacío, escriba su contraseña.
    
3. Seleccione **Iniciar sesión**.
    
## <a name="sign-out-of-skype-for-business"></a>Cerrar la sesión de Skype Empresarial

Cuando haya terminado de usar Skype empresarial, puede cerrar la pantalla, cerrar la sesión de la sesión o salir del programa, todo desde el menú archivo. En la tabla siguiente se explican las diferencias entre estas opciones.
  
|**Opción**|**Qué hace**|**Cómo lo hago**|
|:-----|:-----|:-----|
|Cerrar  <br/> |Cierra la pantalla, pero permite que la sesión de Skype empresarial identificada con su identificador de usuario continúe ejecutándose. El motivo es poder seguir recibiendo notificaciones e interactuando con los demás. <br/> <br/> Puede volver a abrir la pantalla en cualquier momento haciendo clic en el icono de Skype empresarial en la barra de tareas o en el área de notificación de la parte inferior de la pantalla.  <br/> | En la ventana principal de Skype empresarial, realice una de las siguientes acciones: <br/> 1. Haga clic en el botón **Opciones** y, a continuación, seleccione**cerrar** **archivo** > .  <br/> 2. Haga clic en el botón **cerrar** (X) en la esquina superior derecha de la ventana. <br/> |
|Cerrar sesión  <br/> |Finaliza la sesión asociada con su identificador de usuario, pero Skype empresarial continúa ejecutándose en segundo plano. Al cerrar la sesión, aparece la ventana de inicio de sesión.  <br/> **Sugerencia:** Seleccione **eliminar mi información** de inicio de sesión cuando cierre la sesión para quitar el registro de su identificador de inicio de sesión y contraseña del equipo. De este modo tiene que resultar más fácil al equipo técnico ayudar a los usuarios a resolver problemas de inicio de sesión. También puede ayudar a garantizar que la información de inicio de sesión es más segura, ya que resulta más difícil para los usuarios no autorizados iniciar sesión con credenciales ajenas. <br/> |En la ventana principal de Skype empresarial, seleccione el botón **Opciones** y, a continuación, seleccione**Cerrar sesión**en **archivo** > .  <br/> |
|Salir  <br/> |Finaliza la sesión de Skype empresarial y cierra Skype empresarial en su equipo. Después de haber salido, si quiere reiniciar, seleccione **iniciar** > **todos los programas** > Skype empresarial. <br/> |En la ventana principal de Skype empresarial, seleccione el **botón Opciones** y, a continuación, seleccione**salida**de **archivo** > .  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>Iniciar sesión en Skype Empresarial con una tarjeta inteligente

Algunas organizaciones ahora usan un proceso de inicio de sesión en varios pasos, denominado autenticación de dos factores, para aumentar la seguridad de sus usuarios. Si tiene previsto usar esta opción, necesitará una "tarjeta inteligente" para iniciar sesión en Skype empresarial. Las tarjetas inteligentes pueden ser físicas o virtuales:
  
- **Physical** Acerca del tamaño de una tarjeta de crédito. Se inserta en un lector al iniciar sesión.
    
- **Virtual** No es un objeto físico, sino un identificador electrónico que se escribe en un chip especial de su equipo, que, en esencia, crea la tarjeta inteligente en el equipo. Solo disponible para usar con equipos con Windows 8 que contengan el chip TPM (módulo de plataforma segura).
    
### <a name="enroll-your-smart-card"></a>Inscriba su tarjeta inteligente

Antes de poder iniciar sesión con una tarjeta inteligente, la tarjeta debe estar "inscrito", es decir, las credenciales de usuario deben identificarse con la tarjeta. Esto se aplica tanto a tarjetas físicas como virtuales. Es posible que este proceso ya haya sido realizado por el administrador de Skype empresarial Server. Verifica si no estás seguro de que se haya realizado.
  
> [!NOTE]
> Como cada tarjeta inteligente virtual solo está asociada con el dispositivo en el que está instalada, será necesario inscribir una tarjeta independiente para cada equipo con Windows 8 que use. 
  
### <a name="to-manually-enroll-your-smart-card"></a>Inscribir una tarjeta inteligente manualmente

1. Inicie sesión en el equipo en el que ejecutará Skype empresarial.
    
2. Con Internet Explorer, vaya a la página de inscripción Web de la entidad emisora de certificados de su organización. 
    
    Pida a su administrador de Skype empresarial Server la dirección Web de este recurso si aún no la tiene. La dirección URL tendrá un aspecto similar a https://MyCAeste:. [elnombredesuempresa]. com/certsrv.
    
    > [!NOTE]
    > Si está usando Internet Explorer 10, es posible que tenga que ver este sitio web en el modo de compatibilidad. 
  
3. Cuando se le solicite que inicie sesión en la página de certificación, inicie sesión con su cuenta de dominio (en lugar de como administrador del equipo).
    
4. En la página principal del sitio web, seleccione **Solicitar un certificado**.
    
5. Seleccione **Solicitud avanzada**.
    
6. Seleccione **Crear y enviar una solicitud a esta CA** y haga clic en **Siguiente**.
    
7. Ahora verá una página denominada estación de inscripción de tarjeta inteligente. Apruebe la solicitud para instalar el control ActiveX y luego complete el formulario Solicitud de certificado avanzada de la siguiente manera:
    
    a. Seleccione **Usuario de tarjeta inteligente** de la lista desplegable **Plantilla de certificado**.
    
    b. Seleccione **Crear conjunto de claves nuevo**.
    
    c. Busque la información del fabricante en la etiqueta de la tarjeta inteligente y seleccione el fabricante de la lista desplegable **CSP**.
    
    d. Seleccione **CSP** como formato de solicitud, si aún no está seleccionado.
    
    &. Seleccione **SHA1** en la lista desplegable algoritmo hash, si aún no está seleccionada.
    
    f. Asigne un nombre a su certificado que reconozca y haga clic en **Enviar**.
    
8. Inserte la tarjeta inteligente vacía en el lector de tarjetas junto a la estación de inscripción y haga clic en **Inscribir**.
    
9. Cuando se le indique, escriba su número de identificación personal (PIN) y haga clic en **Aceptar**.
    
    > [!NOTE]
    > Si el representante de soporte técnico no le asignó un PIN especial para usar en la inscripción de la tarjeta inteligente, use el valor de PIN predeterminado de la tarjeta, que es 12345678. 
  
10. Seleccione la opción para forzar al usuario (usted) a que cambie el PIN la primera vez que use la tarjeta inteligente.
    
11. Inserte la tarjeta inteligente vacía en el lector de tarjetas junto a la estación de inscripción y haga clic en **Inscribir**.
    
12. Cuando se le indique, escriba su número de identificación personal (PIN) y haga clic en **Aceptar**.
    
    > [!NOTE]
    > Si el representante de soporte técnico no le asignó un PIN especial para usar en la inscripción de la tarjeta inteligente, use el valor de PIN predeterminado de la tarjeta, que es 12345678. 
  
13. Seleccione la opción para forzar al usuario (usted) a que cambie el PIN la primera vez que use la tarjeta inteligente.
    
14. Haga clic en **Aceptar** para confirmar que el certificado que aparece incluye la información correspondiente.
    
15. Cuando vea la notificación de que se emitió el certificado, haga clic en **Instalar este certificado** para completar el proceso de inscripción.
    
### <a name="sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Iniciar sesión en Skype Empresarial con los credenciales de la tarjeta inteligente

Antes de usar su tarjeta inteligente por primera vez, le recomendamos que haga clic en **eliminar mi información de inicio de sesión** en la página de inicio de sesión de Skype empresarial. De esta manera, se borran todas las credenciales de inicio de sesión almacenadas en el equipo y se elimina una posible fuente de error.
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Iniciar sesión en Skype Empresarial con los credenciales de la tarjeta inteligente

1. Inicie el cliente de Skype empresarial.
    
2. En la pantalla de inicio de sesión, escriba el nombre de la cuenta de usuario para iniciar la sesión en el cuadro **Dirección de inicio de sesión** y haga clic en **Iniciar sesión**.
    
3. Si usa una tarjeta inteligente virtual, omita este paso.
    
    Si usa una tarjeta inteligente física, inserte la tarjeta en el lector de tarjetas inteligentes y, si se lo solicitan, haga clic en **Aceptar** cuando la tarjeta es detectada.
    
4. Escriba el número de PIN para la tarjeta inteligente y haga clic en **Aceptar**.
    
    > [!NOTE]
    > Si no se le asignó un número de PIN para la tarjeta inteligente, use el valor predeterminado, que es 12345678. 
  
## <a name="see-also"></a>Vea también

[Administrar la autenticación en dos fases en Skype empresarial Server](two-factor-authentication.md)
  
[Configurar la autenticación en dos fases en Skype empresarial Server](configure-two-factor.md)
