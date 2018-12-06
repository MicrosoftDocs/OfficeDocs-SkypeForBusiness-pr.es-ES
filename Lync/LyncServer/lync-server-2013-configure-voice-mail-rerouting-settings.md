---
title: "Lync Server 2013: Configurar los valores para volver a enrutar el correo de voz"
TOCTitle: Configurar los valores para volver a enrutar el correo de voz
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48275763
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar los valores para volver a enrutar el correo de voz en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-18_

Las Aplicaciones de sucursal con funciones de supervivencia y los Servidores de sucursal con funciones de supervivencia pueden proporcionar funciones de supervivencia de correo de voz a los usuarios de sucursal durante las interrupciones de WAN, si la Mensajería unificada de Exchange (UM) está instalada en el sitio central y se implementa un Operador automático (AA) de mensajes de la Mensajería unificada de Exchange. Recomendamos que su administrador de Exchange configure el Operador automático para que acepte solo mensajes, con lo cual se deshabilita el resto de la funcionalidad general como, por ejemplo, las transferencias a un usuario o a un operador. También puede usar un AA genérico o un AA personalizado para enrutar la llamada.

Para ver más detalles, consulte la sección "Preparación de la supervivencia de correo de voz" de [Requisitos de resistencia de sitios de sucursal para Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) en la documentación de planeación.

## Para configurar las funciones de supervivencia del correo de voz

1.  Pida al administrador de Exchange que configure el AA de modo que acepte mensajes solamente (en el Shell de Exchange, use el siguiente cmdlet: **Set-UMAutoAttendant \<AA name\> -CallSomeoneEnabled $false**. El parámetro que especifica que se debe permitir dejar mensajes ( *SendVoiceMsgEnabled*) es "true" de forma predeterminada.

2.  En el Shell de administración de Lync Server, use el cmdlet **New-CSVoiceMailReroutingConfiguration** para establecer el número de teléfono del AA como el número de teléfono del operador automático de Mensajería unificada de Exchange en la configuración de reenrutamiento del correo de voz de la Aplicación de sucursal con funciones de supervivencia o la Servidor de sucursal con funciones de supervivencia.
    

    > [!NOTE]
    > Si, más tarde, necesita modificar la configuración de reenrutamiento del correo de voz, use para ello el cmdlet <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG>. Para ver más detalles acerca de <STRONG>New-</STRONG> y <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG>, consulte los temas de ayuda del shell.



3.  Establezca el número de acceso de suscriptor de Mensajería unificada de Exchange correspondiente al plan de marcado de Mensajería unificada de Exchange del usuario de la sucursal como el número de acceso de suscriptor de Mensajería unificada de Exchange en la configuración de reenrutamiento del correo de voz de Aplicación de sucursal con funciones de supervivencia o Servidor de sucursal con funciones de supervivencia.
    

    > [!NOTE]
    > Configure el plan de marcado de los usuarios de Mensajería unificada de Exchange de modo que haya un solo plan de marcado asociado a todos los usuarios de sucursales que necesiten acceder a la funcionalidad de Obtener correo de voz durante una interrupción de WAN.



**Siguiente paso** para las Aplicaciones de sucursal con funciones de supervivencia o los Servidores de sucursal con funciones de supervivencia: [Usuarios particulares en una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).

