---
title: "Definir requisitos de servidores front-end, mensajería instantánea y presencia "
TOCTitle: 'Definir los requisitos de los servidores front-end, la mensajería instantánea y la presencia '
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412956(v=OCS.15)
ms:contentKeyID: 48276565
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definir los requisitos de los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013

 

_**Última modificación del tema:** 2013-10-07_

La tarea principal de la planeación de la mensajería instantánea (MI) y la presencia es comprobar que se dispone de suficientes servidores front-end para los usuarios.

## Habilitar la comunicación con los usuarios externos

Puede aumentar los beneficios de su inversión considerablemente en Lync Server si habilita la comunicación entre sus usuarios y los usuarios externos. Entre los usuarios externos se pueden incluir:

  - **Usuarios remotos**   Los propios usuarios de la organización cuando están trabajando externamente a los firewalls con sus propios portátiles u otros dispositivos de Lync Server.

  - **Usuarios federados**   Usuarios de empresas con las que colabora y que también ejecutan Lync Server. Si desea habilitar a sus usuarios para que se pongan en contacto fácilmente con estos otros usuarios, cree relaciones federadas con estas compañías.

  - **Usuarios públicos**   Usuarios que usan servicios de MI pública, como los proporcionados por la Red de Windows Live de servicios de Internet, Yahoo\! y AOL, y usuarios de proveedores y servidores que usan el protocolo extensible de mensajería y presencia (XMPP), como Google Talk.
    

    > [!NOTE]
    > Tenga en cuenta que quizás sea necesaria otra licencia para la conectividad de MI pública con Windows Live, AOL y Yahoo!.

    
    > [!IMPORTANT]  
	> <ul>
    > <li><p>El 1 de septiembre de 2012, la licencia de suscripción del usuario de Public IM Connectivity de Microsoft Lync (&quot;PIC USL&quot;) dejó de estar disponible para su compra en los contratos nuevos y en las prórrogas de contratos. Los clientes que tengan licencias activas podrán seguir federándose con Yahoo! Messenger hasta la fecha de cierre del servicio. La fecha anunciada para el fin de vida de AOL y Yahoo! es junio de 2014. Para más detalles, vea <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Soporte para la conectividad de mensajería instantánea pública en Lync Server 2013</a>.</p></li>
    > <li><p>PIC USL es una licencia de suscripción por usuario/por mes requerida por Lync Server u Office Communications Server para la federación con Yahoo! Messenger. La posibilidad de Microsoft de proporcionar este servicio depende de la compatibilidad con Yahoo!, cuyo contrato subyacente está llegando a su fin.</p></li>
    > <li><p>Hoy más que nunca, Lync es una herramienta eficaz para conectarse dentro de una organización y con individuos de todo el mundo. La federación con Windows Live Messenger no requiere ninguna licencia de usuario o dispositivo adicional aparte de la CAL estándar de Lync. La federación con Skype se agregará a esta lista, lo que permitirá a los usuarios de Lync conectarse con cientos de millones de personas a través de mensajería instantánea y voz.</p></li>
    > </ul>


Para habilitar uno o todos estos escenarios, debe implementar un servidor perimetral que facilite la habilitación de comunicaciones seguras entre la implementación de Lync Server y los usuarios externos. Los usuarios remotos de su organización y los usuarios de las organizaciones federadas podrán ver la presencia de los demás y comunicarse con MI. Para más información sobre la habilitación de la comunicación con usuarios externos, consulte [Planear acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) en la documentación de planeación.

## Archivado del contenido de MI

Lync Server proporciona características que se pueden usar si la organización debe seguir regulaciones de conformidad. Puede usar el servidor de archivado para archivar el contenido de los mensajes de MI de todos los usuarios de la organización, o solamente de algunos específicos. Para más información, consulte [Planificar el archivado en Lync Server 2013](lync-server-2013-planning-for-archiving.md) en la documentación de planeación.

Si también ha implementado Microsoft Exchange Server 2013, puede integrar el archivado de los datos de Exchange con el archivado de los datos de Lync Server y usar una única herramienta para buscar en ambos tipos de datos archivados. Para más información, consulte [Configuración de Microsoft Lync Server 2013 para utilizar el archivado de Microsoft Exchange Server 2013](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).

