---
title: Usar autenticación de dos factores con Skype para clientes empresariales y Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: 'Resumen: Use la autenticación en dos fases con Skype para Business Server y Skype para la empresa.'
ms.openlocfilehash: 0c66808f22655e3f78a23930adc84dcbc31af6bb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894205"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a>Usar autenticación de dos factores con Skype para clientes empresariales y Skype para Business Server
 
**Resumen:** Usar autenticación de dos factores con Skype para Business Server y Skype para la empresa.
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Iniciar sesión en Skype Empresarial por primera vez

La información de inicio de sesión normalmente se configura automáticamente cuando se instala Skype para la empresa. Pero la primera vez que utilice Skype para la empresa, es posible que deba iniciar manualmente el cliente.
  
### <a name="to-sign-in-for-the-first-time"></a>Iniciar sesión por primera vez

1. Inicie sesión en la red de su organización.
    
2. Seleccione **Iniciar** > **todos los programas** > **Skype para la empresa**.
    
    Aparecerá la pantalla de inicio de sesión.
    
    - Si el cuadro de dirección para inicio de sesión ya está rellenado, confirme que la dirección que aparece es correcta.
    
    - Si no es correcta, o si el cuadro está vacío, escriba la dirección de inicio de sesión (Esto suele ser la misma que la dirección de correo electrónico).
    
    - Si aparece un cuadro de contraseña vacío, escriba su contraseña.
    
3. Seleccione **Iniciar sesión**.
    
## <a name="sign-out-of-skype-for-business"></a>Cerrar la sesión de Skype Empresarial

Cuando haya terminado de usar Skype para la empresa, puede cerrar la presentación, desconectarse de la sesión o salir del programa, todo desde el menú archivo. En la tabla siguiente se explican las diferencias entre estas opciones.
  
|**Opción**|**Qué hace**|**Cómo lo hago**|
|:-----|:-----|:-----|
|Cerrar  <br/> |Cierra la presentación, pero permite la Skype para sesión empresarial identificado con su identificador de continuar con la ejecución de usuario. El motivo es poder seguir recibiendo notificaciones e interactuando con los demás. <br/> <br/> Puede obtener la presentación atrás en cualquier momento haciendo clic en el Skype para el icono de negocio en la barra de tareas o el área de notificación en la parte inferior de la pantalla.  <br/> | En Skype para la ventana principal de negocio, realice una de las siguientes opciones: <br/> 1. Seleccione el botón **Opciones** , a continuación, seleccione **archivo** > **Close**.  <br/> 2. Haga clic en el botón **Cerrar** (X) en la esquina superior derecha de la ventana. <br/> |
|Cerrar sesión  <br/> |Finaliza la sesión asociada con el identificador de usuario, pero Skype para la empresa sigue ejecutándose en segundo plano. Al cerrar la sesión, aparece la ventana de inicio de sesión.  <br/> **Sugerencia:** Seleccione **Eliminar mi información de inicio de sesión** al cerrar la sesión quitar el registro de su identificador de inicio de sesión y la contraseña desde el equipo. De este modo tiene que resultar más fácil al equipo técnico ayudar a los usuarios a resolver problemas de inicio de sesión. También puede ayudar a garantizar que la información de inicio de sesión es más segura, ya que resulta más difícil para los usuarios no autorizados iniciar sesión con credenciales ajenas. <br/> |En Skype para la ventana principal de negocio, seleccione el botón **Opciones** y después seleccione el **archivo** > **Cerrar sesión**.  <br/> |
|Salir  <br/> |Finaliza la Skype para la sesión de negocio y cierra Skype para la empresa en su equipo. Después de salir, si desea reiniciar, seleccione **Iniciar** > > de**Todos los programas** Skype para la empresa. <br/> |En Skype para la ventana principal de negocio, seleccione el botón **Opciones** y después seleccione el **archivo** > **Salir**.  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>Iniciar sesión en Skype Empresarial con una tarjeta inteligente

Algunas organizaciones ahora usan un proceso de inicio de sesión en varios pasos, denominado autenticación de dos factores, para aumentar la seguridad de sus usuarios. Si tiene previsto usar esta opción, necesitará un "tarjetas inteligentes" para iniciar sesión en Skype para la empresa. Las tarjetas inteligentes pueden ser físicos o virtuales:
  
- **Físico** Acerca del tamaño de una tarjeta de crédito. Se inserta en un lector al iniciar sesión.
    
- **Virtual** No es un objeto físico, pero un identificador electrónico que se escribe en un chip especial en su equipo, que se basa en esencia la tarjeta inteligente en su equipo. Disponible sólo para su uso con equipos Windows 8 que contienen el chip de TPM (módulo de plataforma de confianza).
    
### <a name="enroll-your-smart-card"></a>Inscriba su tarjeta inteligente

Antes de que puede iniciar sesión con una tarjeta inteligente, la tarjeta debe ser "inscrito", es decir, sus credenciales de usuario se tienen que se identifican con la tarjeta. Esto se aplica tanto a tarjetas físicas como virtuales. Este proceso, es posible que ya sido a cabo a través de su Skype para el administrador del servidor de negocio. Compruebe con ellos si no está seguro de si el que se ha realizado.
  
> [!NOTE]
> Dado que cada tarjeta inteligente virtual sólo está asociado con el dispositivo se instala en, tendrá una tarjeta independiente que se inscriben para cada equipo de Windows 8 que se utiliza. 
  
### <a name="to-manually-enroll-your-smart-card"></a>Inscribir una tarjeta inteligente manualmente

1. Inicie sesión en el equipo, podrá ejecutar Skype para la empresa en.
    
2. Con Internet Explorer, vaya a la página de inscripción Web de entidad de certificado de la organización. 
    
    Si aún no lo tiene, pida su Skype para el administrador del servidor empresarial para la dirección web de este recurso. La dirección URL será similar a esto: https://MyCA. [yourcompanyname] .com/certsrv.
    
    > [!NOTE]
    > Si usa Internet Explorer 10, debe ver este sitio Web en modo de compatibilidad. 
  
3. Cuando se le pedirá que inicie sesión en la página de certificados, inicie sesión con su cuenta de dominio (en lugar de como administrador de su equipo).
    
4. En la página principal del sitio web, seleccione **Solicitar un certificado**.
    
5. Seleccione **Solicitud avanzada**.
    
6. Seleccione **Crear y enviar una solicitud a esta CA** y haga clic en **Siguiente**.
    
7. Ahora verá una página denominada estación de inscripción de tarjetas inteligentes. Apruebe la solicitud para instalar el control ActiveX y luego complete el formulario Solicitud de certificado avanzada de la siguiente manera:
    
    a. Seleccione **Usuario de tarjeta inteligente** de la lista desplegable **Plantilla de certificado**.
    
    b. Seleccione **Crear conjunto de claves nuevo**.
    
    c. Busque la información del fabricante en la etiqueta de la tarjeta inteligente y seleccione el fabricante de la lista desplegable **CSP**.
    
    d. Seleccione **CSP** como el formato de solicitud, si aún no está seleccionado.
    
    e. Seleccione **sha1** en la lista desplegable algoritmo de Hash, si aún no está seleccionado.
    
    f. Asigne el certificado de un nombre que reconozca y haga clic en **Enviar**.
    
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

Antes de usar su tarjeta inteligente por primera vez, se recomienda que haga clic en **Eliminar mi información de inicio de sesión** en el Skype para la página de inicio de sesión de negocio. De esta forma borra cualquier credenciales de inicio de sesión almacenadas en su equipo y elimina un origen posible de error.
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Iniciar sesión en Skype Empresarial con los credenciales de la tarjeta inteligente

1. Inicie el Skype para clientes empresariales.
    
2. En la pantalla de inicio de sesión, escriba el nombre de la cuenta de usuario para iniciar la sesión en el cuadro **Dirección de inicio de sesión** y haga clic en **Iniciar sesión**.
    
3. Si usa una tarjeta inteligente virtual, omita este paso.
    
    Si usa una tarjeta inteligente física, inserte la tarjeta en el lector de tarjetas inteligentes y, si se lo solicitan, haga clic en **Aceptar** cuando la tarjeta es detectada.
    
4. Escriba el número de PIN para la tarjeta inteligente y haga clic en **Aceptar**.
    
    > [!NOTE]
    > Si no se le asignó un número de PIN para la tarjeta inteligente, use el valor predeterminado, que es 12345678. 
  
## <a name="see-also"></a>Consulte también

[Administrar la autenticación de dos factores en Skype para Business Server](two-factor-authentication.md)
  
[Configuración de autenticación de dos factores en Skype para Business Server](configure-two-factor.md)
