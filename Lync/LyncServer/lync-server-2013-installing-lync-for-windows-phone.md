---
title: 'Lync Server 2013: instalar Lync para Windows Phone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync for Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690996(v=OCS.15)
ms:contentKeyID: 51541513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de018fee2d4e9906c8eee3bd59ff360ce1db94a2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a>Instalar Lync para Windows Phone en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-03_

Lync 2013 para Windows Phone es una aplicación instalable por el usuario que está disponible en el catálogo de soluciones de Windows Phone.

<div>

## <a name="installing-lync-for-windows-mobile"></a>Instalar Lync para Windows Mobile

Puede indicar a los usuarios que instalen Lync 2013 para Windows Phone en sus dispositivos; para ello, debe dirigirlos al catálogo <https://go.microsoft.com/fwlink/p/?linkid=231901>de soluciones de Windows Phone en.

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a>Si usa un registro SRV de DNS para publicar los servicios web Exchange

Para habilitar la integración de Exchange en clientes de Lync, algunas organizaciones publican la dirección URL de los servicios web Exchange con un registro SRV de DNS. El documento "Understanding and Troubleshooting Exchange Integration", disponible en el centro de [https://go.microsoft.com/fwlink/?LinkID=391095](https://go.microsoft.com/fwlink/?linkid=391095)descarga de Microsoft en, describe los escenarios en los que puede ser necesario. Sin embargo, la integración de Exchange para los usuarios de Windows Phone no funcionará en este escenario, porque la plataforma de Windows Phone no admite las búsquedas SRV. Deberá indicar a los usuarios de Windows Phone que especifiquen la dirección URL de los servicios web Exchange en lugar de permitir que el teléfono detecte automáticamente el servidor.

Indique a los usuarios que configuren la configuración de Lync en sus teléfonos Windows de la siguiente manera:

1.  En Windows Phone, en la configuración de Lync, seleccione la pantalla de **Exchange** .

2.  Mueva **el servidor de detección automática** a **desactivado**.

3.  Puntee en el campo vacío y escriba el nombre de dominio completo (FQDN) o la dirección URL de los servicios web Exchange.
    
    <div>
    

    > [!NOTE]  
    > Puede especificar el nombre de dominio completo (FQDN) o la dirección URL completa del servidor de servicios web Exchange. Si especifica el FQDN, el protocolo (https://) y la ruta de acceso de los servicios Web de Exchange (/EWS/Exchange.asmx) se agregan automáticamente. Si la ruta de acceso de los servicios Web de Exchange es diferente, puede especificar la dirección URL completa.

    
    </div>

4.  Cierre la pantalla.

</div>

<div>

## <a name="verifying-mobile-client-installation"></a>Comprobar la instalación del cliente móvil

Después de configurar el cliente e iniciar sesión correctamente, use las siguientes pruebas para comprobar que la instalación de Lync 2013 funciona correctamente en su dispositivo móvil.

**Buscar un contacto en el directorio corporativo**

1.  En la lista de contactos, puntee **Buscar** en la parte inferior.

2.  Busque un contacto que existe solamente en la lista global de direcciones.

3.  Compruebe que el nombre de contacto aparece en los resultados de búsqueda.

**Probar la presencia y la mensajería instantánea**

1.  En la lista de contactos, puntee un contacto.

2.  En la tarjeta de contacto, puntee el icono **MI**.

3.  Compruebe que aparece una ventana de mensajería instantánea (mi) y que puede escribir y enviar un mensaje instantáneo.

**Pobrar la conferencia saliente**

1.  En Outlook, programe una reunión de Lync.

2.  En el dispositivo móvil, abra la invitación de la reunión.

3.  Haga clic en el vínculo de la reunión para unirse.

4.  Responda a la llamada del servicio de conferencia y compruebe que está conectado al audio de la reunión.

**Probar las notificaciones de inserción**

1.  En el dispositivo móvil del usuario A, inicie sesión a Lync con la cuenta del usuario A.

2.  Abra otra aplicación en el dispositivo móvil.

3.  En un cliente distinto, inicie sesión a Lync con la cuenta del usuario B.

4.  Envíe un mensaje instantáneo del usuario B al usuario A:

5.  Compruebe que aparece una notificación de mensaje instantáneo en el dispositivo móvil del usuario A.

</div>

</div>

<span> </span>

</div>

</div>

</div>

