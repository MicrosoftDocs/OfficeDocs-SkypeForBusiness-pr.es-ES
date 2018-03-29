---
title: Usar la autenticación en dos fases con el cliente de Skype Empresarial y Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: 'Resumen: Utilice autenticación de dos factores con Skype para Business Server 2015 y Skype para el negocio.'
ms.openlocfilehash: 6bb2133533b640cd573730ca608f5845164ea282
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server-2015"></a>Usar la autenticación en dos fases con el cliente de Skype Empresarial y Skype Empresarial Server 2015
 
**Resumen:** Utilice la autenticación de dos factores con Skype para Business Server 2015 y Skype para el negocio.
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Iniciar sesión en Skype Empresarial por primera vez

La información de inicio de sesión normalmente se configura automáticamente al instala Skype para el negocio. Pero la primera vez que utilice Skype para el negocio, tendrá que iniciar manualmente el cliente.
  
### <a name="to-sign-in-for-the-first-time"></a>Iniciar sesión por primera vez

1. Inicie sesión en la red de su organización.
    
2. Seleccione **Iniciar** > **todos los programas** > **Skype para el negocio**.
    
    Aparecerá la pantalla de inicio de sesión.
    
    - Si el cuadro de dirección para inicio de sesión ya está rellenado, confirme que la dirección que aparece es correcta.
    
    - Si no es correcta, o si el cuadro está vacío, escriba su dirección de inicio de sesión (Esto suele ser la misma que su dirección de correo electrónico).
    
    - Si aparece un cuadro de contraseña vacío, escriba su contraseña.
    
3. Seleccione **Iniciar sesión**.
    
## <a name="sign-out-of-skype-for-business"></a>Cerrar la sesión de Skype Empresarial

Cuando haya terminado de utilizar Skype para empresas, puede cerrar la presentación, cerrar la sesión de la sesión o salir del programa, todo en el menú archivo. En la tabla siguiente se explican las diferencias entre estas opciones.
  
|**Opción**|**Lo que hace**|**Cómo realizarlo**|
|:-----|:-----|:-----|
|Cerrar  <br/> |Cierra la pantalla pero permite el Skype para la sesión de negocios identificado con el usuario ID continúe ejecutándose. El motivo es poder seguir recibiendo notificaciones e interactuando con los demás. <br/> <br/> Puede obtener la pantalla atrás en cualquier momento haciendo clic en el Skype para icono de negocio en el área de notificación en la parte inferior de la pantalla o en la barra de tareas.  <br/> | En Skype para la ventana principal de la empresa, siga uno de estos procedimientos: <br/> 1. Seleccione el botón **Opciones** , a continuación, seleccione **archivo** > **Cerrar**.  <br/> 2. Haga clic en el botón **Cerrar** (X) en la esquina superior derecha de la ventana. <br/> |
|Cerrar sesión  <br/> |Termina la sesión asociada a su identificador de usuario, pero Skype para el negocio continúa ejecutándose en segundo plano. Al cerrar la sesión, aparece la ventana de inicio de sesión.  <br/> **Sugerencia:** Seleccione **Eliminar mi información de inicio de sesión** al cerrar la sesión quitar el registro de su ID de inicio de sesión y contraseña del equipo. De este modo tiene que resultar más fácil al equipo técnico ayudar a los usuarios a resolver problemas de inicio de sesión. También puede ayudar a garantizar que la información de inicio de sesión es más segura, ya que resulta más difícil para los usuarios no autorizados iniciar sesión con credenciales ajenas. <br/> |En Skype para la ventana principal de la empresa, seleccione el botón **Opciones** y seleccione **archivo** > **Cerrar sesión**.  <br/> |
|Salir  <br/> |Finaliza tu Skype para la sesión de negocio y cierra Skype para el negocio en su equipo. Después de salir, si desea reiniciar, seleccione **Iniciar** > **Todos los programas** > Skype para el negocio. <br/> |En Skype para la ventana principal de la empresa, seleccione el botón **Opciones** y seleccione **archivo** > **Salir**.  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>Iniciar sesión en Skype Empresarial con una tarjeta inteligente

Algunas organizaciones ahora usan un proceso de inicio de sesión en varios pasos, denominado autenticación de dos factores, para aumentar la seguridad de sus usuarios. Si tiene previsto utilizar esta opción, necesitará una "tarjeta inteligente" para iniciar sesión en Skype para el negocio. Tarjetas inteligentes pueden ser físicos o virtuales:
  
- **Física** El tamaño de una tarjeta de crédito. Se inserta en un lector al iniciar sesión.
    
- **Virtual** No es un objeto físico, pero un identificador electrónico que se escribe en un chip especial en su equipo, que se basa en esencia la tarjeta inteligente en el equipo. Disponible sólo para su uso con equipos de Windows 8 que contienen el chip de TPM (módulo de plataforma fiable).
    
### <a name="enroll-your-smart-card"></a>Inscriba su tarjeta inteligente

Antes de que puede iniciar sesión con una tarjeta inteligente, la tarjeta debe ser "inscrito": es decir, tienen las credenciales de usuario para identificarse con la tarjeta. Esto se aplica tanto a tarjetas físicas como virtuales. Este proceso puede ya sido llevado a cabo por su Skype para el Administrador de servidor de negocios 2015. Consulte con ellos si no está seguro de si el que se ha realizado.
  
> [!NOTE]
> Dado que cada tarjeta inteligente virtual sólo está asociado con el dispositivo se instala en, necesitará una tarjeta independiente se inscriba para cada equipo Windows 8. 
  
### <a name="to-manually-enroll-your-smart-card"></a>Inscribir una tarjeta inteligente manualmente

1. Inicie sesión en el equipo, podrá ejecutar Skype para el negocio en.
    
2. Utilizando Internet Explorer, vaya a la página de inscripción Web de entidad emisora de certificados de su organización. 
    
    Pida su Skype para el administrador del servidor de la empresa para la dirección web de este recurso si ya no tienes. La dirección URL será similar a esto: https://MyCA. [yourcompanyname] .com/certsrv.
    
    > [!NOTE]
    > Si utilizas Internet Explorer 10, debe ver este sitio Web en modo de compatibilidad. 
  
3. Cuando se le pedirá que inicie sesión en la página de certificados, inicie sesión utilizando su cuenta de dominio (en lugar de como administrador del equipo).
    
4. En la página principal del sitio web, seleccione **Solicitar un certificado**.
    
5. Seleccione **Solicitud avanzada**.
    
6. Seleccione **Crear y enviar una solicitud a esta CA** y haga clic en **Siguiente**.
    
7. Ahora verá una página denominada estación de inscripción de tarjeta inteligente. Apruebe la solicitud para instalar el control ActiveX y luego complete el formulario Solicitud de certificado avanzada de la siguiente manera:
    
    a. Seleccione **Usuario de tarjeta inteligente** de la lista desplegable **Plantilla de certificado**.
    
    b. Seleccione **Crear conjunto de claves nuevo**.
    
    c. Busque la información del fabricante en la etiqueta de la tarjeta inteligente y seleccione el fabricante de la lista desplegable **CSP**.
    
    d. Seleccione el **CSP** como el formato de solicitud, si aún no está seleccionada.
    
    e. Seleccione **sha1** en la lista desplegable algoritmo de Hash, si aún no está seleccionada.
    
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

Antes de usar su tarjeta inteligente por primera vez, se recomienda que haga clic en **Eliminar mi información de inicio de sesión** en el Skype para la página de inicio de sesión de negocios. Esto borra cualquier credencial de inicio de sesión almacenada en su equipo y elimina una posible fuente de error.
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Iniciar sesión en Skype Empresarial con los credenciales de la tarjeta inteligente

1. Iniciar el Skype para cliente de empresa.
    
2. En la pantalla de inicio de sesión, escriba el nombre de la cuenta de usuario para iniciar la sesión en el cuadro **Dirección de inicio de sesión** y haga clic en **Iniciar sesión**.
    
3. Si usa una tarjeta inteligente virtual, omita este paso.
    
    Si usa una tarjeta inteligente física, inserte la tarjeta en el lector de tarjetas inteligentes y, si se lo solicitan, haga clic en **Aceptar** cuando la tarjeta es detectada.
    
4. Escriba el número de PIN para la tarjeta inteligente y haga clic en **Aceptar**.
    
    > [!NOTE]
    > Si no se le asignó un número de PIN para la tarjeta inteligente, use el valor predeterminado, que es 12345678. 
  
## <a name="see-also"></a>Vea también

#### 

[Administrar la autenticación de dos factores en Skype para Business Server 2015](two-factor-authentication.md)
  
[Configurar la autenticación de dos factores en Skype para Business Server 2015](configure.md)

