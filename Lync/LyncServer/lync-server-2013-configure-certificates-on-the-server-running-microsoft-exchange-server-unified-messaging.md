---
title: 'Lync Server 2013: configurar certificados en el servidor que ejecuta la mensajería unificada de Microsoft Exchange Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc9ed0f51b3f534d5967c7195cc39736a4ecae9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a>Configurar certificados en el servidor que ejecuta la mensajería unificada de Microsoft Exchange Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-26_

Si ha implementado la mensajería unificada de Exchange (UM), como se describe en [planeamiento de la integración de mensajería unificada de Exchange en Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) en la documentación de planeación y desea proporcionar características de mensajería unificada de Exchange a los usuarios de voz de empresa de su organización, puede usar los procedimientos siguientes para configurar el certificado en el servidor que ejecuta la mensajería unificada de Exchange.

<div>


> [!IMPORTANT]  
> En el caso de los certificados internos, tanto los servidores que ejecutan Lync Server 2013 como los servidores que ejecutan Microsoft Exchange deben tener certificados de entidad raíz de confianza que sean de confianza mutuamente. La entidad de certificación (CA) puede ser la misma o una entidad de certificación diferente, siempre que los servidores tengan el certificado raíz de la entidad de certificación registrado en su almacén de certificados de entidad de certificación raíz de confianza.



</div>

El servidor de Exchange debe estar configurado con un certificado de servidor para poder conectarse a Lync Server 2013:

1.  Descargue el certificado de CA para el servidor de Exchange.

2.  Instale el certificado de CA para el servidor de Exchange.

3.  Compruebe que la entidad emisora de certificados se encuentra en la lista de entidades emisoras raíz de confianza del servidor de Exchange.

4.  Cree una solicitud de certificado para el servidor de Exchange e instale el certificado.

5.  Asigne el certificado para el servidor de Exchange.

<div>

## <a name="to-download-the-ca-certificate"></a>Para descargar el certificado de la entidad emisora

1.  En el servidor que ejecuta la mensajería unificada de Exchange, haga clic en **Inicio**, haga clic en **ejecutar**, escriba **http://\<nombre del servidor\>CA**emisora/certsrv y, a continuación, haga clic en **Aceptar**.

2.  En **seleccionar una tarea**, haga clic en **descargar un certificado de CA, una cadena de certificados o una CRL**.

3.  En **descargar un certificado de CA, una cadena de certificados o una CRL**, seleccione el **método de codificación para base 64**y, después, haga clic en **Descargar certificado de CA**.
    
    <div>
    

    > [!NOTE]  
    > También puede especificar la codificación de las reglas de codificación distintivas (DER) en este paso. Si selecciona la codificación DER, el tipo de archivo en el paso siguiente de este procedimiento y en el paso 10 de <STRONG>para instalar el certificado de la entidad emisora</STRONG> es. p7b en lugar de. cer.

    
    </div>

4.  En el cuadro de diálogo **descarga de archivos** , haga clic en **Guardar**y, a continuación, guarde el archivo en el disco duro del servidor. (El archivo tendrá una extensión. cer o. p7b, en función de la codificación que haya seleccionado en el paso anterior).

</div>

<div>

## <a name="to-install-the-ca-certificate"></a>Para instalar el certificado de CA

1.  En el servidor que ejecuta la mensajería unificada de Exchange, abra Microsoft Management Console (MMC) haciendo clic en **Inicio**, haga clic en **Ejecutar**, escriba **MMC** en el cuadro **abrir** y, a continuación, haga clic en **Aceptar**.

2.  En el menú **archivo** , haga clic en **Agregar o quitar complemento**y, a continuación, haga clic en **Agregar**.

3.  En el cuadro **Agregar complementos independientes** , haga clic en **certificados**y, a continuación, haga clic en **Agregar**.

4.  En el cuadro de diálogo **Complemento de certificados**, haga clic en **Cuenta de equipo** y luego haga clic en **Siguiente**.

5.  En el cuadro de diálogo **seleccionar equipo** , compruebe que la casilla **equipo local: (el equipo en el que se está ejecutando esta consola)** está activada y, a continuación, haga clic en **Finalizar**.

6.  Haga clic en **cerrar**y, a continuación, en **Aceptar**.

7.  En el árbol de consola, expanda **certificados (equipo local)**, expanda **entidades emisoras raíz de confianza**y, a continuación, haga clic en **certificados**.

8.  Haga clic con el botón secundario en **certificados**, seleccione **todas las tareas**y haga clic en **importar**.

9.  Haga clic en **Siguiente**.

10. Haga clic en **examinar** para buscar el archivo y, a continuación, haga clic en **siguiente**. (El archivo tendrá una extensión. cer o. p7b, en función de la codificación que haya seleccionado en el paso 3 de **para descargar el certificado de la entidad emisora**.

11. Haga clic en **colocar todos los certificados en el siguiente almacén**.

12. Haga clic en **examinar**y seleccione **entidades emisoras de certificados raíz de confianza**.

13. Haga clic en **siguiente** para comprobar la configuración y, a continuación, haga clic en **Finalizar**.

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a>Para comprobar que la entidad emisora está en la lista de entidades emisoras raíz de confianza

1.  En el servidor que ejecuta la mensajería unificada de Exchange, en MMC expanda **certificados (equipo local)**, expanda **entidades emisoras raíz de confianza**y, a continuación, haga clic en **certificados**.

2.  En el panel de detalles, compruebe que la entidad emisora está en la lista de entidades emisoras de confianza.

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a>Para configurar la mensajería unificada de Exchange Server 2013 con Lync Server

1.  Para obtener más información, consulte "integrar la mensajería unificada de Exchange 2013 con Lync Server" [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)en la documentación de Exchange Server en.

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a>Para crear una solicitud de certificado e instalar el certificado en Exchange Server 2007 (SP1)

1.  En el servidor que ejecuta la mensajería unificada de Exchange, haga clic en **Inicio**, haga clic en **Ejecutar**,**\>** escriba **http://\<** nombre del servidor CA emisora/certsrv y, a continuación, haga clic en **Aceptar**.

2.  En **seleccionar una tarea**, haga clic en **solicitar un certificado**.

3.  En **solicitar un certificado**, haga clic en **solicitud de certificado avanzada**.

4.  En **solicitud de certificado avanzada**, haga clic en **crear y enviar una solicitud a esta CA**.

5.  En **solicitud de certificado avanzada**, seleccione **servidor Web** u otra plantilla de certificado de servidor configurada para la autenticación de servidor.

6.  En **información de identificación para plantillas sin conexión**, en el cuadro **nombre** , escriba el nombre de dominio completo (FQDN) del servidor de Exchange.
    
    <div>
    

    > [!NOTE]  
    > Debe especificar el nombre de dominio completo del servidor de Exchange para que las comunicaciones funcionen.

    
    </div>

7.  En **Opciones de clave**, haga clic en la casilla **almacenar el certificado en el almacén de certificados del equipo local** .

8.  Haga clic en el botón **Enviar** en la parte inferior de la Página Web.

9.  En el cuadro de diálogo que se abre pidiendo confirmación, haga clic en **sí**.

10. En la página certificado emitido, en **certificado emitido**, haga clic en **instalar este certificado**.

11. En el cuadro de diálogo que se abre pidiendo confirmación, haga clic en **sí**.

12. Compruebe que aparece el mensaje "su nuevo certificado se ha instalado correctamente".

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a>Para crear un certificado en Exchange Server 2010

1.  Inicie sesión en el servidor que ejecuta la mensajería unificada de Exchange con los derechos de usuario apropiados. Para obtener más información, vea "permisos de acceso [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)de cliente" en.

2.  Para crear el certificado, consulte los procedimientos siguientes:
    
    1.  "Crear un nuevo certificado de Exchange" en[http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)
    
    2.  "Importar un certificado de Exchange" en[http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)
    
    <div>
    

    > [!NOTE]  
    > Para el <STRONG>nombre del sujeto</STRONG>del certificado, debe especificar el FQDN del servidor de Exchange para que funcionen las comunicaciones.

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a>Para asignar el certificado en Exchange Server 2007 (SP1)

1.  En el servidor que ejecuta la mensajería unificada de Exchange, abra MMC.

2.  En el árbol de consola, expanda **personal** y, a continuación, haga clic en **certificados**.

3.  En el panel de detalles, compruebe que aparece certificado personal.

4.  Haga doble clic en el certificado para leer sus detalles y comprobar que es válido.
    
    <div>
    

    > [!NOTE]  
    > Puede demorar unos minutos antes de que el certificado se muestre como válido.

    
    </div>

5.  Reinicie el servicio de mensajería unificada de Microsoft Exchange.
    
    <div>
    

    > [!NOTE]  
    > El servidor que ejecuta la mensajería unificada de Exchange Server 2007 SP1 recupera automáticamente el certificado correcto.

    
    </div>

6.  Abra el visor de eventos y busque el identificador de evento 1112, que especifica qué certificado ha recuperado el servidor que ejecuta la mensajería unificada de Exchange Server 2007 SP1.

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a>Para asignar el certificado en Exchange Server 2010

1.  Inicie sesión en el servidor que ejecuta la mensajería unificada de Exchange con los derechos de usuario apropiados. Para obtener más información, vea "permisos de acceso [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)de cliente" en.

2.  Para obtener el procedimiento para asignar el certificado, consulte "asignar servicios a un certificado" [http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497)en.

</div>

</div>

<span> </span>

</div>

</div>

</div>

