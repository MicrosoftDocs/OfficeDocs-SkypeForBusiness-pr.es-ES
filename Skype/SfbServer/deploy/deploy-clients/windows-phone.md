---
title: Instalar y probar Skype Empresarial para Windows Phone
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 54289bbe-97e7-44bf-8611-4e740fc5b998
description: 'Resumen: Aprenda a instalar y probar Skype empresarial en Windows Phone.'
ms.openlocfilehash: 2796f1664ec20142bd8f9399830836c8c284ac67
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278287"
---
# <a name="install-and-test-skype-for-business-for-windows-phone"></a>Install and test Skype for Business for Windows Phone
 
**Resumen:** Obtenga información sobre cómo instalar y probar Skype empresarial en su Windows Phone.
  
La aplicación de Skype empresarial para Windows Phone proporciona la presencia, la mensajería instantánea (mi) y las llamadas de voz y vídeo de Skype empresarial a dispositivos Windows Mobile. Los usuarios con Lync 2013 obtendrán la aplicación actualizada automáticamente o se les pedirá que la actualicen manualmente, en función de la configuración de usuario. Los nuevos usuarios pueden descargarla desde el [Marketplace de Windows Phone](https://go.microsoft.com/fwlink/p/?linkid=231901). La aplicación de Skype empresarial para Windows Phone solo está disponible en Windows Phone 8,1 y versiones posteriores.
  
Antes de dirigir a los usuarios de su organización a descargar la aplicación, deseará ejecutar las siguientes pruebas para asegurarse de que está integrada correctamente en su entorno. 
  
## <a name="install-skype-for-business-windows-phone-81"></a>Instalar Skype empresarial Windows Phone 8,1

1. Vaya a [Windows Phone 8 update central](https://www.windowsphone.com/en-us/how-to/wp8/update-central) para actualizar el teléfono a windows phone 8,1.
    
2. Desde el teléfono, vaya a la **tienda**y busque **Skype empresarial**.
    
3. Toque **Instalar**. 
    
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Iniciar sesión en Skype Empresarial por primera vez

1. En la pantalla **Inicio** , deslice el dedo hacia la izquierda para ver las aplicaciones instaladas, busque Skype empresarial para Windows Phone y, a continuación, pulse el icono para abrir la aplicación.
    
2. Escriba su dirección de inicio de sesión (por ejemplo, user@domain.com) y la contraseña y, a continuación, pulse **hecho**.
    
     Es posible que deba proporcionar un nombre de usuario y una dirección de inicio de sesión. El nombre de usuario es lo que usted usa para iniciar sesión en la red de su organización, ya sea user@domain.com o dominio\nombredeusuario.
    
3. En la pantalla **Programa para la mejora de la experiencia del usuario**, toque **Unirse** para enviar datos anónimos sobre los problemas con la aplicación y su uso a Microsoft o bien **No, gracias** si prefiere no participar.
    
4. En la pantalla **No se pierda nunca sus llamadas del trabajo**, introduzca su número de teléfono móvil con los códigos de país o región. Cuando Skype empresarial para Windows Phone no pueda usar una red Wi-Fi o de datos móviles para realizar una llamada de audio o vídeo, se le llamará automáticamente a este número y se conectará a la parte de audio de la llamada.
    
5. Pulse **siguiente** y revise la notificación y la configuración de acceso de la agenda telefónica:
    
   - **Notificaciones push** Recibe una alerta cuando recibas un nuevo mensaje instantáneo o una llamada. Normalmente **Activado** (recomendado).
    
     > [!IMPORTANT]
     > Si desactiva esta configuración, no recibirá notificaciones de mensajes instantáneos, llamadas u otras alertas de Skype empresarial para Windows Phone, a menos que la aplicación esté activa. 
  
   - **Permitir acceso a la libreta de teléfonos** Busque contactos en su teléfono móvil cuando busque contactos en Skype empresarial para Windows Phone.
    
6. Pulse **siguiente** para empezar a usar Skype empresarial para Windows Phone.
    
    [¿Necesita ayuda para iniciar sesión?](https://support.office.com/article/6b827683-ad55-471a-bd4b-3d4ec098bf75)
    
## <a name="verify-mobile-client-installation"></a>Comprobar la instalación del cliente móvil

Después de configurar el cliente e iniciar sesión correctamente, use las siguientes pruebas para comprobar que la instalación de Skype empresarial para Windows Phone funciona correctamente en su dispositivo móvil.
  
### <a name="search-for-a-contact-in-the-corporate-directory"></a>Buscar un contacto en el directorio corporativo

1. En la lista de contactos, pulse en **Buscar**.
    
2. Busque un contacto que existe solamente en la lista global de direcciones.
    
3. Compruebe que el nombre de contacto aparece en los resultados de búsqueda.
    
### <a name="test-instant-messaging-and-presence"></a>Probar la mensajería instantánea y la presencia

1. En la lista de contactos, pulse un contacto.
    
2. En la tarjeta de contacto, pulse la mensajería instantánea (mi) ![Icono para la mensajería instantánea en Skype Empresarial](../../media/90f8d5fa-7968-4ef7-bf5b-dddf9b893905.png)icono.
    
3. Compruebe que aparece una ventana de mensajería instantánea y que puede escribir y enviar un mensaje.
    
### <a name="test-dial-out-conferencing"></a>Probar la conferencia saliente

1. En Outlook, programe una reunión de Skype empresarial.
    
2. En su Windows Phone, abra la invitación de la reunión.
    
3. Haga clic en el vínculo de la reunión para unirse.
    
4. Responda a la llamada del servicio de conferencia y compruebe que está conectado al audio de la reunión.
    
### <a name="test-push-notifications"></a>Probar las notificaciones de inserción

1. Seleccione dos cuentas de usuario diferentes para esta prueba. 
    
2. En el Windows Phone del usuario A, inicie sesión en Skype empresarial para Windows Phone con la cuenta del usuario A.
    
3. Abra otra aplicación en el dispositivo.
    
4. En un cliente diferente, como el cliente de escritorio, inicie sesión en Skype empresarial con la cuenta del usuario B.
    
5. Envíe un mensaje instantáneo del usuario B al usuario A.
    
6. Compruebe que la notificación de mi aparece en el dispositivo móvil del usuario A.
    
## <a name="remove-skype-for-business-from-your-windows-phone"></a>Quitar Skype empresarial de Windows Phone

Para quitar la aplicación de Skype empresarial para Windows Phone de su dispositivo móvil: 
  
1. En la pantalla de inicio, pase el dedo para ver la lista de aplicaciones. 
    
2. Puntee y mantenga presionada la aplicación de Skype empresarial para Windows Phone y ****, a continuación, seleccione Desinstalar.
    


