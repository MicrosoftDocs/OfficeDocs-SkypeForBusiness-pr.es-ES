---
title: Instalar y probar Skype Empresarial para Windows Phone
ms.reviewer: ''
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 54289bbe-97e7-44bf-8611-4e740fc5b998
description: 'Resumen: Obtenga información sobre cómo instalar y probar Skype para la empresa en su Windows Phone.'
ms.openlocfilehash: f944b5d80928bd1454893dedc3bb4d56ba2d3033
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214866"
---
# <a name="install-and-test-skype-for-business-for-windows-phone"></a>Install and test Skype for Business for Windows Phone
 
**Resumen:** Obtenga información sobre cómo instalar y probar Skype para la empresa en su Windows Phone.
  
El Skype para la aplicación empresarial para Windows Phone aporta Skype para profesionales presencia, mensajería instantánea (IM) y voz y vídeo de llamada para dispositivos móviles de Windows. Los usuarios con Lync 2013 obtendrán la aplicación actualizada automáticamente o se les pedirá que la actualicen manualmente, en función de la configuración de usuario. Nuevos usuarios pueden descargarlo desde el [Marketplace de Windows Phone](https://go.microsoft.com/fwlink/p/?linkid=231901). El Skype para la aplicación empresarial para Windows Phone sólo está disponible en Windows Phone 8.1 y versiones posteriores.
  
Antes de dirigir a los usuarios de la organización para descargar la aplicación, desea ejecutar las siguientes pruebas para asegurarse de que se integra correctamente en su entorno. 
  
## <a name="install-skype-for-business-windows-phone-81"></a>Instalar Skype para profesionales de Windows Phone 8.1

1. Vaya a [Windows Phone 8 actualizar central](https://www.windowsphone.com/en-us/how-to/wp8/update-central) para actualizar el teléfono para Windows Phone 8.1.
    
2. Desde el teléfono, vaya a la **tienda**y buscar **Skype para la empresa**.
    
3. Toque **Instalar**. 
    
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Iniciar sesión en Skype Empresarial por primera vez

1. En la pantalla de **Inicio** , haga pasar el dedo izquierda para ver las aplicaciones instaladas, buscar Skype para empresarial para Windows Phone y, a continuación, puntee en el icono para abrir la aplicación.
    
2. Escriba su dirección de inicio de sesión (por ejemplo, user@domain.com) y la contraseña y, a continuación, puntee en **Listo**.
    
     Es posible que deba proporcionar un nombre de usuario y una dirección de inicio de sesión. El nombre de usuario es lo que se utiliza para iniciar sesión en la red de su organización, ya sea user@domain.com o dominio\nombre de usuario.
    
3. En la pantalla **Programa para la mejora de la experiencia del usuario**, toque **Unirse** para enviar datos anónimos sobre los problemas con la aplicación y su uso a Microsoft o bien **No, gracias** si prefiere no participar.
    
4. En la pantalla **No se pierda nunca sus llamadas del trabajo**, introduzca su número de teléfono móvil con los códigos de país o región. Cuando Skype para empresarial para Windows Phone no puede usar una red de conexión de datos o Wi-Fi para realizar una llamada de audio o vídeo, podrá ser automáticamente la llamada a este número y conectado a la parte de audio de la llamada.
    
5. Puntee en **siguiente** y revise la notificación y la configuración de acceso de la libreta de teléfonos:
    
   - **Notificaciones de inserción** Cuando reciba una llamada o un nuevo mensaje instantáneo, recibirá una alerta. Normalmente **Activado** (recomendado).
    
     > [!IMPORTANT]
     > Si activa esta opción desactivada, que no se le notifique de mensajes instantáneos, las llamadas u otro Skype para alertas de negocio para Windows Phone a menos que la aplicación está activa. 
  
   - **Permitir el acceso de libreta de teléfonos** Buscar contactos en el teléfono móvil al buscar contactos en Skype para profesionales de Windows Phone.
    
6. Puntee en **siguiente** para comenzar a usar Skype para profesionales de Windows Phone.
    
    [¿Necesita ayuda para iniciar sesión?](https://support.office.com/article/6b827683-ad55-471a-bd4b-3d4ec098bf75)
    
## <a name="verify-mobile-client-installation"></a>Comprobar la instalación del cliente móvil

Después de configurar al cliente e iniciar sesión correctamente, use las siguientes pruebas para comprobar que la instalación de Skype para empresarial para Windows Phone funciona correctamente en su dispositivo móvil.
  
### <a name="search-for-a-contact-in-the-corporate-directory"></a>Buscar un contacto en el directorio corporativo

1. En la lista de contactos, pulse en **Buscar**.
    
2. Busque un contacto que existe solamente en la lista global de direcciones.
    
3. Compruebe que el nombre de contacto aparece en los resultados de búsqueda.
    
### <a name="test-instant-messaging-and-presence"></a>Probar la mensajería instantánea y la presencia

1. En la lista de contactos, pulse un contacto.
    
2. En la tarjeta de contacto, puntee en la mensajería instantánea (mi) ![Icono para la mensajería instantánea en Skype Empresarial](../../media/90f8d5fa-7968-4ef7-bf5b-dddf9b893905.png)icono.
    
3. Compruebe que aparece una ventana de mensajería instantánea y que puede escribir y enviar un mensaje.
    
### <a name="test-dial-out-conferencing"></a>Probar la conferencia saliente

1. En Outlook, programe una Skype para la reunión de negocios.
    
2. En su Windows Phone, abra la invitación de la reunión.
    
3. Haga clic en el vínculo de la reunión para unirse.
    
4. Responda a la llamada del servicio de conferencia y compruebe que está conectado al audio de la reunión.
    
### <a name="test-push-notifications"></a>Probar las notificaciones de inserción

1. Seleccione dos cuentas de usuario diferentes para esta prueba. 
    
2. En del usuario de Windows Phone, inicie sesión en Skype para empresarial para Windows Phone con la cuenta del usuario.
    
3. Abra otra aplicación en el dispositivo.
    
4. En un cliente distinto, como el cliente de escritorio, inicie sesión en Skype para la empresa con la cuenta del usuario B.
    
5. Envíe un mensaje instantáneo del usuario B al usuario A.
    
6. Compruebe que la notificación de mensajería instantánea aparece en el dispositivo móvil del usuario.
    
## <a name="remove-skype-for-business-from-your-windows-phone"></a>Quitar Skype para la empresa de su Windows Phone

Para quitar el Skype para la aplicación empresarial para Windows Phone desde su dispositivo móvil: 
  
1. En la pantalla de inicio, pase el dedo para ver la lista de aplicaciones. 
    
2. Puntee y mantenga el Skype para aplicaciones de negocio para Windows Phone y, a continuación, seleccione **desinstalar**.
    


