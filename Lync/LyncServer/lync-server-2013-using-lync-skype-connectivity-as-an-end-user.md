---
title: 'Lync Server 2013: Usar la conectividad de Lync y Skype como usuario final'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Lync-Skype connectivity as an end user
ms:assetid: ad22f731-118c-4349-8790-b1a72941cbdd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440175(v=OCS.15)
ms:contentKeyID: 57793365
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d2bf4584f3332171942f941cc382d22bb6a8db7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-lync-skype-connectivity-in-lync-server-2013-as-an-end-user"></a>Usar la conectividad de Lync y Skype como usuario final en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-12-27_

Lync: la conectividad de Skype permite que los usuarios de Skype y los usuarios de Lync se agreguen entre sí como contactos, intercambiar mensajes instantáneos y realizar llamadas de audio y vídeo. Cuando un usuario de Skype agrega un usuario de Lync, un usuario de Skype creará un contacto en Skype que contenga el identificador uniforme de recursos (URI) del Protocolo de inicio de sesión (SIP) del usuario de Lync. Por el contrario, cuando un usuario de Lync agrega un contacto de Skype, el usuario de Lync creará un contacto en Lync que contendrá la cuenta Microsoft (MSA) del usuario de Skype, pero no el nombre de usuario de Skype.

**¿Qué es un MSA?** Para poder comunicarse con los contactos de Lync, los usuarios de Skype deben iniciar sesión en Skype con una cuenta de Microsoft (anteriormente denominada Windows Live ID).Una cuenta de Microsoft consta de la combinación de una dirección de correo electrónico y una contraseña, que también puede usar para iniciar sesión en servicios como la tecnología de almacenamiento de Microsoft OneDrive, Windows Phone, el servicio de juegos en línea de Microsoft Xbox LIVE y la mensajería de Microsoft Outlook. y el cliente de colaboración (y, anteriormente, servicio de correo electrónico basado en Internet de Microsoft hotmail o Windows Live Messenger).Si usa una dirección de correo electrónico y una contraseña para iniciar sesión en estos u otros servicios, ya tiene una cuenta de Microsoft.Para obtener más información sobre cómo crear una cuenta de Microsoft, consulte la página de suscripción [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061)de la cuenta de Microsoft en. Puede fusionar su cuenta de Skype con su cuenta de Microsoft para el inicio de sesión único en una gran variedad de aplicaciones y servicios. Una vez que se combina la cuenta, un usuario de Skype puede enviar una solicitud de contacto a los usuarios de Lync.

<div>


> [!IMPORTANT]  
> Para que los usuarios de Lync y Skype se comuniquen entre sí, deben cumplirse los siguientes requisitos: 
> <UL>
> <LI>
> <P>Los usuarios de Skype deben iniciar sesión en su cliente de Skype con una cuenta de Microsoft (MSA).</P>
> <LI>
> <P>Los usuarios de Lync deben habilitar la conectividad de mensajería instantánea pública por parte del administrador de Lync.</P>
> <LI>
> <P>Cuando un usuario de Skype agregue un contacto de Lync, compruebe que aparece la palabra Lync debajo del nombre del contacto. Indica que se ha encontrado un URI de Lync.</P>
> <LI>
> <P>Cuando un usuario de Skype agrega un contacto de Lync y se devuelven cero resultados de búsqueda para ese dominio de Lync, es posible que el proceso de aprovisionamiento de PIC no se haya completado, o que aún no se haya configurado el dominio de Lync.</P>
> <LI>
> <P>Según la configuración de privacidad de los usuarios de Lync y Skype, los mensajes instantáneos, de video y de presencia no funcionarán hasta que todos los usuarios acepten los nuevos contactos.</P></LI></UL>



</div>

**Para agregar un contacto de Skype a Lync 2013**

1.  En Lync, haga clic en **Agregar un contacto y agregue un contacto que no está en mi organización**.

2.  En la lista de proveedores de contactos disponibles, seleccione **Skype**.

3.  En el campo **dirección de mensajería instantánea** , escriba la cuenta de Microsoft (MSA) del usuario de Skype.

4.  En el cuadro de lista **Agregar a grupo de contactos** , seleccione un grupo de contactos al que agregar el usuario.

5.  En el cuadro desplegable **establecer relación de privacidad** , seleccione la configuración de contacto adecuada y, a continuación, haga clic en **Aceptar**.

6.  El usuario aparecerá ahora como un contacto en Lync. Seleccione el usuario, haga clic con el botón derecho en el nombre de usuario y, a continuación, haga clic en **Ver tarjeta de contacto** para ver las propiedades del usuario. Ahora puedes establecer una llamada de audio o vídeo con el nuevo usuario de Skype.

Para obtener más información sobre la compatibilidad de los contactos, vea [Agregar un contacto en Lync](https://support.office.com/en-us/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a).

Cuando la cuenta Microsoft de un usuario de Skype usa un nombre de dominio personalizado, como <strong>Bob@contoso.com</strong> , un usuario de Lync puede agregar esa cuenta Microsoft a Lync de dos maneras:

1.  Use el icono **Agregar un contacto** o

2.  Use el campo **buscar a alguien o un salón, o marcar un número** .

En cada instancia, el usuario de Lync debe escribir el correo electrónico del usuario de Skype en el siguiente formato: <strong>usuario (nombre de dominio) @msn. com</strong> .

<div>


> [!IMPORTANT]  
> Este paso no es necesario para las cuentas de Microsoft que usan los siguientes nombres de dominio: <STRONG>@live. com, @hotmail. com o @outlook. com</STRONG>. Para obtener más información sobre los nombres de dominio personalizados admitidos, consulte <A href="https://support.microsoft.com/kb/897567">dominios de mensajería instantánea pública admitidos</A>.



</div>

**Para agregar un contacto de Skype a Lync al usar un nombre de dominio personalizado**

1.  En Lync, haga clic en **Agregar un contacto y agregue un contacto que no está en mi organización**.

2.  En la lista de proveedores de contactos disponibles, seleccione **Skype**.

3.  En el campo **dirección de mensajería instantánea** , escriba la cuenta de Microsoft (MSA) del usuario de Skype con el formato <strong>usuario (nombre de dominio) @msn. com</strong>. Así, para el usuario bob@contoso.com, la entrada <strong>sería Bob (contoso. com) @msn.<strong> com.

4.  En el cuadro de lista desplegable **Agregar a grupo de contactos** , seleccione un grupo de contactos al que agregar el usuario.

5.  En el cuadro de lista desplegable **establecer relación de privacidad** , seleccione la configuración de contacto adecuada y, a continuación, haga clic en **Aceptar**.

6.  Un usuario de Lync también puede usar el campo **Buscar en alguien o una sala, o marcar un número** en Lync y agregar una dirección similar a la siguiente <strong>(nombre de dominio) @msn. com</strong> . Por lo tanto, para la cuenta de Microsoft bob@contoso.com, la entrada sería <strong>Bob (contoso. com) @msn. com</strong> .

7.  Siga los pasos 4 y 5 descritos anteriormente en este procedimiento para agregar el contacto a un grupo de contactos y para seleccionar la relación de privacidad adecuada.

**Para agregar un contacto de Lync a Skype**

1.  Inicia sesión en Skype. El usuario de Skype debe haber iniciado sesión en su cliente de Skype con una cuenta de Microsoft (MSA).

2.  Seleccione el icono Añadir contactos.

3.  Escriba el URI SIP del usuario de Lync. Por ejemplo, bob@contoso.com.

4.  Cuando Skype encuentre la coincidencia en los resultados de la búsqueda, busque la palabra **Lync** debajo del nombre del usuario de Lync. Esto indica que Skype ha encontrado correctamente el URI del SIP del cliente de Lync. Haga clic en el nombre.

5.  En la esquina superior derecha de la ventana, haga clic en Agregar a contactos.

6.  El nuevo contacto se agregará a tu lista de contactos, pero verás un signo de interrogación en lugar del icono de estado hasta que acepten tu solicitud. Cuando el nuevo contacto acepte su solicitud, podrá ver cuándo está conectado, iniciar conversaciones de mensajería instantánea y realizar llamadas de audio y vídeo.
    
    <div>
    

    > [!IMPORTANT]  
    > El administrador de Lync Server debe configurar las opciones de directiva del usuario de Lync para permitir las solicitudes entrantes. De lo contrario, el usuario de Lync no recibirá solicitudes de contacto del usuario de Skype. En función de la configuración de la configuración de directiva del usuario de Lync, la solicitud para agregar el usuario de Skype aparecerá en la pestaña <STRONG>nuevo</STRONG> del cliente de Lync. Para comenzar a comunicarse con el usuario de Skype, el usuario de Lync debe agregar el usuario de Skype a la lista de favoritos o a una lista de contactos. La imagen siguiente muestra la ubicación de la <STRONG>nueva</STRONG> pestaña en el cliente de Lync.

    
    </div>

Un usuario de Lync debe configurar las alertas de Lync para asegurarse de que las solicitudes enviadas desde un usuario de Skype puedan ser detectadas por el usuario de Lync. Para configurar las alertas de Lync, realice el siguiente procedimiento.

**Para configurar las alertas de Lync**

1.  Desde el cliente Lync, haga clic en el icono **Opciones** .

2.  Seleccione **alertas**.

3.  En **alertas generales**, Active avisarme **cuando alguien me agregue a su lista de contactos**.

4.  En **contactos que no usan Lync**, seleccione **permitir invitaciones pero bloquear todas las demás comunicaciones**.

5.  Haga clic en **Aceptar** para cerrar la ventana Opciones.

</div>

<span> </span>

</div>

</div>

</div>

