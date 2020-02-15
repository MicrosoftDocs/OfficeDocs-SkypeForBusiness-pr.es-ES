---
title: 'Lync Server 2013: configurar certificados para servidores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for servers
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398995(v=OCS.15)
ms:contentKeyID: 48185531
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e2fd3ce8c229fad2f990d5f295e4c4454ef153e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-servers-in-lync-server-2013"></a>Configurar certificados para servidores en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-17_

Para completar correctamente este procedimiento, debe haber iniciado sesión como un usuario miembro del grupo RTCUniversalServerAdmins o tener los permisos correctos delegados. Para obtener más información sobre cómo delegar permisos, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md). Es probable que deba pertenecer a otros grupos en función de su organización y los requisitos para solicitar certificados. Consúltelo con el grupo que administra la entidad de certificación de la infraestructura de clave pública (PKI).

<div>


> [!NOTE]  
> Lync Server 2013 incluye compatibilidad con la serie SHA-2 (SHA-2, que usa longitudes implícitas de 224, 256, 384 o 512 bits) de algoritmos hash y de firma de compendio para conexiones de clientes que ejecutan Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista o Sistemas operativos Windows XP, además de Lync Phone Edition. Para admitir el acceso externo mediante el conjunto de aplicaciones SHA-2, el certificado externo lo emite una entidad de certificación pública que también puede emitir un certificado con el mismo Resumen de longitud de bits.



</div>

<div>


> [!WARNING]  
> La selección de qué algoritmo de firma y Resumen de hash depende de los clientes y los servidores que usarán el certificado, y de otros equipos y dispositivos con los que los clientes y servidores se comunicarán con quién también debe saber cómo usar los algoritmos que se usan en el emisor. Para obtener información sobre qué longitudes de síntesis son compatibles en el sistema operativo y en algunas<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>aplicaciones cliente, consulte.



</div>

Cada servidor Standard Edition o servidor front-end requiere hasta cuatro certificados: el certificado oAuthTokenIssuer, un certificado predeterminado, un certificado Web interno y un certificado externo Web. No obstante, es posible solicitar y asignar un solo certificado predeterminado con las entradas de nombre alternativo de sujeto apropiadas, así como con el certificado oAuthTokenIssuer. Para obtener más información sobre los requisitos de certificado, consulte [requisitos de certificados para servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md). Para obtener más información sobre cómo solicitar, asignar e instalar el certificado oAuthTokenIssuer, consulte [Managing Server-to-Server Authentication (OAuth) and Partner Applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

Use el siguiente procedimiento para solicitar, asignar e instalar los certificados de servidor Standard Edition o front-end. Repita el procedimiento para cada servidor front-end.

<div>


> [!IMPORTANT]  
> En el siguiente procedimiento se describe cómo configurar certificados desde una PKI de empresa interna implementada por su organización y sin necesidad de conexión para procesar solicitudes. Para obtener información sobre cómo obtener certificados de una entidad de certificación pública, consulte <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">requisitos de certificados para servidores internos en Lync Server 2013</A> en la documentación referente a la planeación. Además, este procedimiento describe cómo solicitar, asignar e instalar certificados durante la configuración del servidor front-end. Si ha solicitado certificados por adelantado, tal como se describe en la sección <A href="lync-server-2013-request-certificates-in-advance-optional.md">solicitar certificados de antemano (opcional) para Lync Server 2013</A> de esta documentación de implementación, o no usa una PKI de empresa interna implementada en la organización para obtener certificados, debe modificar este procedimiento según corresponda.



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a>Para configurar certificados para un servidor front-end

1.  En el Asistente para la implementación de Lync Server, haga clic en **Ejecutar** junto al **paso 3: solicitar, instalar o asignar certificados**.

2.  En la página **Asistente para certificados**, haga clic en **Solicitud**.

3.  En la página **Solicitud de certificado**, haga clic en **Siguiente**.

4.  En la página **Solicitudes retrasadas o inmediatas**, acepte la opción predeterminada **Envíe la solicitud inmediatamente a una entidad de certificación en línea** haciendo clic en **Siguiente**. La CA interna con inscripción en línea automática debe estar disponible si selecciona esta opción. Si elige la opción para retrasar la solicitud, se le pedirá un nombre y una ubicación para guardar el archivo de solicitud de certificado. La solicitud de certificado debe ser presentada y procesada por una CA de su organización o bien por una CA pública. Después, tendrá que importar la respuesta de certificado y asignarla al rol de certificado apropiado.

5.  En la página elegir una entidad de certificación **(CA)** , seleccione la opción **seleccionar una entidad de certificación de la lista detectada en el entorno** y, a continuación, seleccione una entidad de certificación conocida (mediante registro en los servicios de dominio de Active Directory) de la lista. O bien, seleccione la opción **Especificar otra entidad de certificación**, escriba el nombre de otra CA en el cuadro y haga clic en **Siguiente**.

6.  En la página **Cuenta de entidad de certificación**, se solicitan sus credenciales para solicitar y procesar la solicitud de certificado en la CA. Debe haber determinado si es necesario un nombre de usuario y una contraseña para solicitar un certificado por adelantado. Su administrador de CA tendrá la información necesaria y es posible que deba ayudarle en este paso. Si tiene que especificar credenciales alternativas, seleccione la casilla, escriba un nombre de usuario y una contraseña en los cuadros de texto y haga clic en **Siguiente**.

7.  En la página **Especificar plantilla de certificado alternativa**, haga clic en **Siguiente** para usar la plantilla de servidor web predeterminada.
    
    <div>
    

    > [!NOTE]  
    > Si su organización ha creado una plantilla para usar como alternativa a la plantilla de la CA de servidor web predeterminada, seleccione la casilla y escriba el nombre de la plantilla alternativa. Necesitará el nombre de la plantilla definido por el administrador de CA.

    
    </div>

8.  En la página **Nombre y configuración de seguridad**, especifique un **Solo nombre** que debe permitirle identificar el certificado y el propósito. Si lo deja en blanco, se generará un nombre automáticamente. Establezca la **Longitud en bits** de la clave o acepte el valor predeterminado de 2048 bits. Active la casilla **Marcar la clave privada del certificado como exportable** si determina que el certificado y la clave privada deben moverse o copiarse a otros sistemas y haga clic en **Siguiente**.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 tiene requisitos mínimos para una clave privada exportable. Uno de estos sitios se encuentra en los servidores perimetrales en un grupo de servidores, donde el servicio de autenticación relé multimedia usa copias del certificado, en lugar de certificados individuales para cada instancia en el grupo de servidores.

    
    </div>

9.  En la página **Información de la organización**, si lo desea, proporcione información de la organización y después haga clic en **Siguiente**.

10. En la página **Información geográfica**, si lo desea, escriba información geográfica y después haga clic en **Siguiente**.

11. En la página **Nombre del sujeto o nombres alternativos del sujeto**, revise los nombres alternativos del sujeto que se van a agregar y haga clic en **Siguiente**.

12. En la página **Configuración del dominio SIP**, active la casilla **Dominio SIP** y haga clic en **Siguiente**.

13. En la página **Configurar nombres alternativos de sujeto adicionales**, agregue los nombres alternativos de sujeto adicionales que desee, incluido cualquiera que piense que puede ser necesario para dominios SIP adicionales en el futuro, y haga clic en **Siguiente**.

14. En la página **Resumen de la solicitud de certificados**, revise la información del resumen. Si la información es correcta, haga clic en **Siguiente**. Si necesita corregir o modificar una configuración, haga clic en **Atrás** para ir a la página pertinente y realizar la corrección o modificación.

15. En la página **Ejecución de comandos**, haga clic en **Siguiente**.

16. En la página **Estado de solicitud del certificado en línea**, revise la información devuelta. Tenga en cuenta que el certificado se emitió e instaló en el almacén de certificados local. Si se informa de que se ha emitido e instalado, pero que no es válido, asegúrese de que el certificado raíz de la CA se haya instalado en el almacén de CA raíz de confianza del servidor. Consulte la documentación de la CA para obtener información sobre cómo recuperar un certificado de CA de raíz de confianza. Si necesita ver el certificado recuperado, haga clic en **Ver detalles del certificado**. La casilla **Asignar este certificado a los usos de certificado de Lync Server** está activada de forma predeterminada. Si desea asignar manualmente el certificado, active la casilla y haga clic en **Finalizar**.

17. Si ha activado la casilla **Asignar este certificado a los usos de certificado de Lync Server** en la página anterior, aparecerá la página **Asignación del certificado**. Haga clic en **Siguiente**.

18. En la página **Almacén de certificados**, seleccione el certificado solicitado. Si desea ver el certificado, haga clic en **Ver detalles del certificado** y en **Siguiente** para continuar.
    
    <div>
    

    > [!NOTE]  
    > Si en la página <STRONG>Estado de solicitud del certificado en línea</STRONG> se ha notificado algún problema con el certificado, como que el certificado no es válido, ver el certificado real puede resultarle de ayuda para resolver el problema. Dos problemas específicos que pueden hacer que un certificado no sea válido son que falte el certificado de CA de raíz de confianza mencionado anteriormente o que falte una clave privada asociada con el certificado. Consulte la documentación de su CA para resolver estos dos problemas.

    
    </div>

19. En la página **Resumen de asignación de certificados** , revise la información que se presenta para asegurarse de que este sea el certificado que debe asignarse y, a continuación, haga clic en **siguiente**.

20. En la página **Ejecutando comandos**, revise el resultado del comando. Haga clic en **Ver registro** si desea revisar el proceso de asignación o si se ha emitido algún error o advertencia. Cuando termine, haga clic en **Finalizar**.

21. En la página **Asistente para certificados**, compruebe que el **Estado** del certificado sea “Asignado” y haga clic en **Cerrar**.

</div>

<div>

## <a name="see-also"></a>Vea también


[Requisitos de infraestructura de certificados para Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

