---
title: Instalar y probar Skype Empresarial para Windows Phone
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 54289bbe-97e7-44bf-8611-4e740fc5b998
description: 'Resumen: Conozca cómo instalar y probar Skype para los negocios en el Windows Phone.'
ms.openlocfilehash: c3f9fcf20726c4fd33dc4de462b64a1397373a0f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="install-and-test-skype-for-business-for-windows-phone"></a>Skype Empresarial Server 2015: instalar y probar Skype Empresarial para Windows Phone
 
**Resumen:** Aprenda a instalar y probar Skype para los negocios en el Windows Phone.
  
El Skype para el negocio para Windows Phone app trae Skype para negocios presencia, mensajería instantánea (IM) y voz y video llamada a dispositivos móviles de Windows. Los usuarios con Lync 2013 obtendrán la aplicación actualizada automáticamente o se les pedirá que la actualicen manualmente, en función de la configuración de usuario. Nuevos usuarios pueden descargarla desde el [Marketplace de Windows Phone](https://go.microsoft.com/fwlink/p/?linkid=231901). El Skype para el negocio para Windows Phone app sólo está disponible en Windows Phone 8.1 y posterior.
  
Antes de dirigir los usuarios de su organización para descargar la aplicación, desea ejecutar las siguientes pruebas para asegurarse de que se integre adecuadamente en su entorno. 
  
## <a name="install-skype-for-business-windows-phone-81"></a>Instalar Skype para Windows Phone de negocio 8.1

1. Vaya a [Windows Phone 8 actualizar central](https://www.windowsphone.com/en-us/how-to/wp8/update-central) para actualizar tu teléfono a Windows Phone 8.1.
    
2. Desde tu teléfono, vaya a la **tienda**y buscar **Skype para el negocio**.
    
3. Toque **Instalar**. 
    
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Iniciar sesión en Skype Empresarial por primera vez

1. En la pantalla de **Inicio** , Deslizar izquierda para ver las aplicaciones instaladas, buscar Skype para negocios para Windows Phone y, a continuación, puntee en el icono para abrir la aplicación.
    
2. Introduzca su dirección de inicio de sesión (por ejemplo, user@domain.com) y la contraseña y, a continuación, puntee en **hecho**.
    
     Es posible que deba proporcionar un nombre de usuario y una dirección de inicio de sesión. El nombre de usuario es lo que utilizas para iniciar sesión en la red de su organización, user@domain.com o dominio\nombre de usuario.
    
3. En la pantalla **Programa para la mejora de la experiencia del usuario**, toque **Unirse** para enviar datos anónimos sobre los problemas con la aplicación y su uso a Microsoft o bien **No, gracias** si prefiere no participar.
    
4. En la pantalla **No se pierda nunca sus llamadas del trabajo**, introduzca su número de teléfono móvil con los códigos de país o región. Cuando Skype para negocios para Windows Phone puede utilizar una red celular de datos o Wi-Fi para realizar una llamada de audio o vídeo, podrá ser automáticamente la llamada a este número y conectado a la parte de audio de la llamada.
    
5. Puntee en **siguiente** y revise la notificación y la configuración de acceso de la libreta de teléfonos:
    
  - **Notificaciones de inserción** Recibirá una alerta cuando reciba una llamada o mensajería instantánea nueva. Normalmente **Activado** (recomendado).
    
    > [!IMPORTANT]
    > Si desactivar estos valores, usted no recibirá notificaciones de IMs, llamadas u otra Skype para alertas de negocio para Windows Phone, a menos que la aplicación está activa. 
  
  - **Permitir el acceso de libreta de teléfonos** Buscar contactos en tu teléfono móvil al buscar contactos en Skype para negocios para Windows Phone.
    
6. Puntee en **siguiente** para empezar a utilizar Skype para negocios para Windows Phone.
    
    [¿Necesitas ayuda para registrarte?](https://support.office.com/article/6b827683-ad55-471a-bd4b-3d4ec098bf75)
    
## <a name="verify-mobile-client-installation"></a>Comprobar la instalación del cliente móvil

Después de configurar al cliente e iniciar sesión correctamente, utilice las siguientes pruebas para comprobar que la instalación de Skype para negocios para Windows Phone funciona correctamente en su dispositivo móvil.
  
### <a name="search-for-a-contact-in-the-corporate-directory"></a>Buscar un contacto en el directorio corporativo

1. En la lista de contactos, pulse en **Buscar**.
    
2. Busque un contacto que existe solamente en la lista global de direcciones.
    
3. Compruebe que el nombre de contacto aparece en los resultados de búsqueda.
    
### <a name="test-instant-messaging-and-presence"></a>Probar la mensajería instantánea y la presencia

1. En la lista de contactos, pulse un contacto.
    
2. En la ficha de contacto, puntee en la mensajería instantánea (IM) ![Icono para la mensajería instantánea en Skype Empresarial](../../media/90f8d5fa-7968-4ef7-bf5b-dddf9b893905.png)icono.
    
3. Compruebe que aparece una ventana de mensajería instantánea y que puede escribir y enviar un mensaje.
    
### <a name="test-dial-out-conferencing"></a>Probar la conferencia saliente

1. En Outlook, programar un Skype para la reunión de negocios.
    
2. En su Windows Phone, abra la invitación de la reunión.
    
3. Haga clic en el vínculo de la reunión para unirse.
    
4. Responda a la llamada del servicio de conferencia y compruebe que está conectado al audio de la reunión.
    
### <a name="test-push-notifications"></a>Probar las notificaciones de inserción

1. Seleccione dos cuentas de usuario diferentes para esta prueba. 
    
2. De usuario del Windows Phone, iniciar sesión en Skype para negocios para Windows Phone con la cuenta del usuario.
    
3. Abra otra aplicación en el dispositivo.
    
4. En un cliente diferente, como el cliente de escritorio, inicie sesión en Skype para empresas con la cuenta de usuario de B.
    
5. Envíe un mensaje instantáneo del usuario B al usuario A.
    
6. Compruebe que aparece la notificación de IM en el dispositivo móvil del usuario.
    
## <a name="remove-skype-for-business-from-your-windows-phone"></a>Quitar Skype para el negocio de su Windows Phone

Para quitar el Skype para el negocio para Windows Phone app desde tu dispositivo móvil: 
  
1. En la pantalla de inicio, pase el dedo para ver la lista de aplicaciones. 
    
2. Puntee y mantenga el Skype para aplicaciones de negocios para Windows Phone y, a continuación, seleccione **desinstalar**.
    
## <a name="see-also"></a>Vea también

#### 


[Cómo comenzar con Skype para negocios para Windows Phone 8.1]()

