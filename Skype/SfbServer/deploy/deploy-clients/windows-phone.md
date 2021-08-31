---
title: Instalar y probar Skype Empresarial para Windows Phone
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 54289bbe-97e7-44bf-8611-4e740fc5b998
description: 'Summary: Learn how to install and test Skype Empresarial on your Windows Phone.'
ms.openlocfilehash: 53a06d80deb99c5f05a9f7a21ab5a5fd171e2797
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727329"
---
# <a name="install-and-test-skype-for-business-for-windows-phone"></a>Instalar y probar Skype Empresarial para Windows Phone
 
**Resumen:** Obtenga información sobre cómo instalar y probar Skype Empresarial en su Windows Phone.
  
La Skype Empresarial para Windows Phone ofrece Skype Empresarial presencia, mensajería instantánea (MI) y llamadas de voz y vídeo a Windows dispositivos móviles. Los usuarios con Lync 2013 recibirán la aplicación actualizada automáticamente o se les pedirá que la actualicen manualmente, según la configuración del usuario. Los nuevos usuarios pueden descargarlo desde [Windows Phone Marketplace](https://go.microsoft.com/fwlink/p/?linkid=231901). La Skype Empresarial para Windows Phone solo está disponible en Windows Phone 8.1 y versiones posteriores.
  
Antes de dirigir a los usuarios de la organización a descargar la aplicación, querrás ejecutar las siguientes pruebas para asegurarte de que esté correctamente integrada en el entorno. 
  
## <a name="install-skype-for-business-windows-phone-81"></a>Instalar Skype Empresarial Windows Phone 8.1

1. Vaya a [Windows Phone 8 update central](https://www.windowsphone.com/en-us/how-to/wp8/update-central) para actualizar el teléfono a Windows Phone 8.1.
    
2. Desde el teléfono, vaya a la **Tienda** y busque **Skype Empresarial**.
    
3. Pulsa **Instalar**. 
    
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Inicie sesión en Skype Empresarial inicio de sesión por primera vez

1. En la **pantalla Inicio,** desliza el dedo hacia la izquierda para ver las aplicaciones instaladas, busca Skype Empresarial para Windows Phone y, a continuación, pulsa el icono para abrir la aplicación.
    
2. Escriba la dirección de inicio de sesión (por ejemplo, user@domain.com) y la contraseña y, a continuación, **puntee Listo**.
    
     Es posible que deba proporcionar un nombre de usuario y una dirección de inicio de sesión. El nombre de usuario es lo que se usa para iniciar sesión en la red de la organización, ya sea user@domain.com o dominio\nombredeusuario.
    
3. En la pantalla Programa de  **mejora** de la experiencia del cliente, pulsa Unirse para enviar datos anónimos sobre problemas de la aplicación y el uso a Microsoft, o **No** gracias si prefieres no participar.
    
4. En la **pantalla Nunca te pierdas las llamadas de** trabajo, escribe tu número de teléfono móvil con códigos de país y región. Cuando Skype Empresarial para Windows Phone puede usar una red de datos de Wi-Fi o de telefonía móvil para realizar una llamada de audio o vídeo, se le llamará automáticamente en este número y se conectará a la parte de audio de la llamada.
    
5. Pulsa **Siguiente** y revisa la configuración de acceso a la notificación y la libreta de teléfonos:
    
   - **Notificaciones de inserción** Obtener una alerta cuando reciba una nueva mensajería instantánea o llamada. Normalmente **On** (recomendado).
    
     > [!IMPORTANT]
     > Si desactivas esta configuración, no se te notificarán las IMs, las llamadas u otras alertas de Skype Empresarial para Windows Phone a menos que la aplicación esté activa. 
  
   - **Permitir el acceso a la libreta de teléfonos** Busque contactos en su teléfono móvil cuando busque contactos en Skype Empresarial para Windows Phone.
    
6. Pulsa **Siguiente** para empezar a usar Skype Empresarial para Windows Phone.
    
    [¿Necesita ayuda para iniciar sesión?](https://support.office.com/article/6b827683-ad55-471a-bd4b-3d4ec098bf75)
    
## <a name="verify-mobile-client-installation"></a>Comprobar la instalación de cliente móvil

Después de configurar el cliente e iniciar sesión correctamente, use las siguientes pruebas para comprobar que la instalación de Skype Empresarial para Windows Phone funciona correctamente en el dispositivo móvil.
  
### <a name="search-for-a-contact-in-the-corporate-directory"></a>Buscar un contacto en el directorio corporativo

1. En la lista Contactos, pulsa **Buscar**.
    
2. Busque un contacto que existe solamente en la lista global de direcciones.
    
3. Compruebe que el nombre de contacto aparece en los resultados de búsqueda.
    
### <a name="test-instant-messaging-and-presence"></a>Probar la presencia y la mensajería instantánea

1. En la lista de contactos, puntee un contacto.
    
2. En la tarjeta de contacto, pulsa la mensajería instantánea (MI) ![Icono de mensajería instantánea en Skype Empresarial.](../../media/90f8d5fa-7968-4ef7-bf5b-dddf9b893905.png).
    
3. Compruebe que aparece una ventana de mensajería instantánea y que puede escribir y enviar una mensajería instantánea.
    
### <a name="test-dial-out-conferencing"></a>Pobrar la conferencia saliente

1. En Outlook, programe una Skype Empresarial reunión.
    
2. En el Windows Phone, abra la invitación a la reunión.
    
3. Haga clic en el vínculo de la reunión para unirse.
    
4. Responda a la llamada del servicio de conferencia y compruebe que está conectado al audio de la reunión.
    
### <a name="test-push-notifications"></a>Probar las notificaciones de inserción

1. Seleccione dos cuentas de usuario diferentes para esta prueba. 
    
2. En la cuenta de usuario A Windows Phone, inicie sesión en Skype Empresarial para Windows Phone con la cuenta del usuario A.
    
3. Abre otra aplicación en el dispositivo.
    
4. En otro cliente, como el cliente de escritorio, inicie sesión en Skype Empresarial con la cuenta del usuario B.
    
5. Envíe un mensaje instantáneo del usuario B al usuario A:
    
6. Compruebe que la notificación de mensajería instantánea aparece en el dispositivo móvil del usuario A.
    
## <a name="remove-skype-for-business-from-your-windows-phone"></a>Quitar Skype Empresarial de la Windows Phone

Para quitar la Skype Empresarial para Windows Phone de tu dispositivo móvil: 
  
1. En la pantalla de inicio, desliza el dedo para ver la lista de aplicaciones. 
    
2. Mantenga presionada la Skype Empresarial para Windows Phone y, a continuación, seleccione **Desinstalar**.
    


