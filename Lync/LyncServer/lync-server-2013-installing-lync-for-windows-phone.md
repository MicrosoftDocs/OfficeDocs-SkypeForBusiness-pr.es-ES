---
title: Instalar Lync para Windows Phone
TOCTitle: Instalar Lync para Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh690996(v=OCS.15)
ms:contentKeyID: 52061727
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Instalar Lync para Windows Phone

 

_**Última modificación del tema:** 2016-12-08_

Lync 2013 para Windows Phone es una aplicación que el usuario puede instalar y que está disponible en el Marketplace de Windows Phone.

## Instalar Lync para Windows Mobile

Puede indicar a sus usuarios que instalen Lync 2013 para Windows Phone en sus dispositivos remitiéndoles al Marketplace de Windows Phone, en <http://go.microsoft.com/fwlink/?linkid=231901>.

## Si utiliza un registro de DNS SRV para publicar en servicios Web Exchange

Para habilitar la integración de Exchange para clientes de Lync, algunas organizaciones publican la dirección URL de servicios Web Exchange usando un registro DNS SRV. En el documento "Información y solución de problemas de Microsoft Exchange Server Integration" disponible en el Centro de descarga de Microsoft en [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095), se describen escenarios en los que puede ser necesario. Sin embargo, la integración de Exchange para los usuarios de Windows Phone no funcionará en este escenario porque la plataforma Windows Phone no es compatible con las búsquedas SRV. Tendrá que indicar a los usuarios de Windows Phone que especifiquen la dirección URL de servicios Web Exchange en lugar de dejar que sea el teléfono el que detecte automáticamente el servidor.

Indique a los usuarios que definan las opciones de configuración de Lync en su Windows Phone como se indica a continuación:

1.  En Windows Phone, en la configuración de Lync, seleccione la pantalla **Exchange**.

2.  Cambie **Detectar servidor automáticamente** a **Desactivado**.

3.  Pulse en el campo vacío y escriba un nombre de dominio completo (FQDN) o una dirección URL para servicios Web Exchange.
    

    > [!NOTE]
    > Puede especificar el nombre de dominio completo (FQDN) o la dirección URL completa de su servidor de servicios Web Exchange. Si especifica el FQDN, el protocolo (https://) y la ruta de servicios Web Exchange (/ews/exchange.asmx) se agregan automáticamente. Si su ruta de servicios Web Exchange es diferente, puede especificar la URL completa.



4.  Cierre la ventana.

## Comprobar la instalación del cliente móvil

Después de configurar el cliente e iniciar sesión correctamente, realice las pruebas siguientes para comprobar que la instalación de Lync 2013 funciona correctamente en su dispositivo móvil.

**Buscar un contacto en el directorio corporativo**

1.  En la lista de contactos, puntee **Buscar** en la parte inferior.

2.  Busque un contacto que existe solamente en la lista global de direcciones.

3.  Compruebe que el nombre de contacto aparece en los resultados de búsqueda.

**Probar la mensajería instantánea y la presencia**

1.  En la lista de contactos, puntee un contacto.

2.  En la tarjeta de contacto, puntee el icono **MI**.

3.  Compruebe que aparece una ventana de mensajería instantánea (MI) y que puede escribir y enviar un mensaje instantáneo.

**Probar la conferencia saliente**

1.  En Outlook, programe una reunión de Lync.

2.  En el dispositivo móvil, abra la invitación de la reunión.

3.  Haga clic en el vínculo de la reunión para unirse.

4.  Responda a la llamada del servicio de conferencia y compruebe que está conectado al audio de la reunión.

**Probar las notificaciones de inserción**

1.  En un dispositivo móvil del usuario A, inicie sesión en Lync con la cuenta de usuario A.

2.  Abra otra aplicación en el dispositivo móvil.

3.  En un cliente distinto, inicie sesión en Lync con la cuenta del usuario B.

4.  Envíe un mensaje instantáneo del usuario B al usuario A:

5.  Compruebe que la notificación de mensaje instantáneo aparece en el dispositivo móvil del usuario A.

