---
title: 'Lync Server 2013: Instrucciones para integrar mensajería unif. local y Lync Server'
TOCTitle: Instrucciones para integrar mensajería unificada local y Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398656(v=OCS.15)
ms:contentKeyID: 48275866
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Instrucciones para integrar mensajería unificada local y Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Los siguientes procedimientos recomendados e instrucciones debe tenerse en cuenta cuando implemente Telefonía IP empresarial:

> [!IMPORTANT]  
> Mensajería unificada de Exchange (UM) admite solo IPv6 si también está usando UCMA 4.



  - Implemente un servidor Standard Edition de Lync Server 2013 o un Grupo de servidores front-end. Para ver más detalles acerca de la instalación, consulte [Implementar Lync Server 2013](lync-server-2013-deploying-lync-server.md) en la documentación sobre implementación.

  - Colabore con los administradores de Exchange para confirmar las tareas que realizará cada uno y así garantizar una integración correcta y homogénea.

  - Implemente los roles de servidor del buzón de Exchange en cada bosque de Mensajería unificada de Exchange (UM) donde desee habilitar los usuarios para Mensajería unificada de Exchange. Para obtener información detallada acerca de cómo instalar los roles de servidor de Exchange, consulte la documentación de Microsoft Exchange Server 2013
    
    > [!IMPORTANT]  
    > Cuando se instala Mensajería unificada de Exchange (UM), se configura para usar un certificado autofirmado.<br />
    > Sin embargo, el certificado autofirmado no habilita Lync Server 2013 y Mensajería unificada de Exchange de modo que confíen mutuamente en el otro, por lo que es necesario solicitar un certificado independiente de una entidad de certificación en el que confíen ambos servidores.


  - Si Lync Server 2013 y Mensajería unificada de Exchange se instalan en diferentes bosques, configure cada bosque de Exchange de modo que confíe en el bosque de Lync Server 2013 y el bosque de Lync Server 2013, de modo que confíe en cada bosque de Exchange. Configure también las opciones de Mensajería unificada de Exchange de los usuarios en los objetos de usuario del bosque de Lync Server 2013; lo habitual es usar un script o una herramienta de otro bosque, como Identity Lifecycle Manager (ILM).

  - Si es necesario, instale la Consola de administración de Exchange de modo que administre los servidores de mensajería unificada.

  - Obtenga números de teléfono válidos para Outlook Voice Access y el operador automático.

  - Si está usando una versión de Mensajería unificada de Exchange anterior a Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordine los nombres de los planes de marcado SIP URI de Mensajería unificada de Exchange y los planes de marcado de Enterprise Voice.

## Implementación de servidores redundantes de mensajería unificada de Exchange

> [!IMPORTANT]  
> Se recomienda implementar un mínimo de dos servidores donde se esté ejecutando la mensajería unificada de Exchange por cada plan de marcado URI del SIP de Mensajería unificada de Exchange que configure en la organización. Además de ofrecer más capacidad, implementar servidores redundantes proporciona alta disponibilidad. En el caso de que se produzca un error en un servidor, Lync Server 2013 se puede configurar de modo que realice la conmutación por error a otro servidor.



Los siguientes ejemplos de configuraciones ofrecen resistencia a la mensajería unificada de Exchange.

**Ejemplo 1: resistencia de la mensajería unificada de Exchange**

![Ejemplo 1 de Mensajería unificada de Exchange](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Ejemplo 1 de Mensajería unificada de Exchange")

En el Ejemplo 1, los servidores de mensajería unificada de Exchange 1 y 2 están habilitados en el centro de datos de Tukwila, y los servidores de mensajería unificada de Exchange 3 y 4 están habilitados en el centro de datos de Dublín. En el caso de que se produzca una interrupción de la mensajería unificada de Exchange en Tukwila, los registros de sistemas de nombre de dominio (DNS) A de los servidores 1 y 2 deben estar configurados para apuntar, respectivamente, a los servidores 3 y 4. En el caso de que se produzca una interrupción de la mensajería unificada de Exchange en Dublín, los registros DNS A de los servidores 3 y 4 deben estar configurados para apuntar, respectivamente, a los servidores 1 y 2.


> [!NOTE]
> En el Ejemplo 1, debe asignar también uno de los siguientes certificados a cada servidor de mensajería unificada de Exchange: 
> <UL>
> <LI>
> <P>Use un certificado con un carácter comodín en el Nombre alternativo de sujeto (SAN).</P>
> <LI>
> <P>Ponga el nombre de dominio completo (FQDN) de cada uno de los cuatro servidores de mensajería unificada de Exchange en el SAN.</P></LI></UL>



**Ejemplo 2: resistencia de la mensajería unificada de Exchange**

![Ejemplo 2 de Mensajería unificada de Exchange](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Ejemplo 2 de Mensajería unificada de Exchange")

En el Ejemplo 2, en condiciones normales de funcionamiento, los servidores de mensajería unificada de Exchange 1 y 2 están habilitados en el centro de datos de Tukwila, y los servidores de mensajería unificada de Exchange 3 y 4 están habilitados en el centro de datos de Dublín. Los cuatro servidores están incluidos en el plan de marcado URI del SIP de los usuarios de Tukwila; sin embargo, los servidores 3 y 4 están deshabilitados. En el caso de que se produzca una interrupción de la mensajería unificada de Exchange en Tukwila, por ejemplo, los servidores 1 y 2 de mensajería unificada de Exchange deben deshabilitarse y los servidores 3 y 4 de mensajería unificada de Exchange deben habilitarse para que el tráfico de mensajería unificada de Exchange de Tukwila se enrute a los servidores de Dublín.

Para obtener detalles acerca de cómo habilitar o deshabilitar la mensajería unificada en Exchange 2013, vea Microsoft Lync Server Preview disponible en [http://go.microsoft.com/fwlink/?linkid=265372\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=265372%26clcid=0xc0a).

Para ver más detalles acerca de cómo habilitar o deshabilitar la mensajería unificada en Microsoft Exchange Server 2010, consulte:

  - "Habilitar la mensajería unificada en Exchange 2010" en [http://go.microsoft.com/fwlink/?linkid=204418\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=204418%26clcid=0xc0a).

  - "Deshabilitar la mensajería unificada en Exchange 2010" en [http://go.microsoft.com/fwlink/?linkid=204416\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=204416%26clcid=0xc0a).

## Vea también

#### Conceptos

[Proceso de implementación de la integración de la mensajería unificada local y Lync Server 2013](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)

