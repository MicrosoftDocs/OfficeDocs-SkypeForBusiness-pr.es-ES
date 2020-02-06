---
title: Planear la integración de la mensajería unificada de Exchange en Skype Empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: 'Resumen: Revise este tema mientras planea la integración de Skype empresarial Server con Exchange 2013 o 2016.'
ms.openlocfilehash: 1ae6ad10f1e817b9ace0240c79d09251a23dd61c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815868"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>Planear la integración de la mensajería unificada de Exchange en Skype Empresarial

**Resumen:** Revise este tema mientras planea la integración de Skype empresarial Server con Exchange 2013 o 2016.

Skype empresarial Server admite la integración con mensajería unificada de Exchange (UM) para combinar la mensajería de voz y la mensajería de correo electrónico en una sola infraestructura de mensajería. En Exchange, la mensajería unificada de Exchange (UM) es una de las diversas funciones de Exchange Server que puede instalar y configurar.

En Microsoft Exchange Server 2013 y 2016, la mensajería unificada de Exchange se ejecuta como un servicio en un servidor de buzones de Exchange. Para las implementaciones de Skype empresarial Server Enterprise Voice, la mensajería unificada combina mensajería de voz y mensajería de correo electrónico en una sola tienda a la que los usuarios pueden obtener acceso desde un teléfono (Outlook Voice Access) o desde un equipo informático. Mensajería unificada y Skype empresarial Server trabajan juntos para proporcionar contestación de llamadas, Outlook Voice Access y los servicios de operador automático para usuarios de telefonía IP empresarial.

> [!NOTE]
> La mensajería unificada de Exchange sigue disponible en Skype empresarial Server 2019 al integrar la 2019 de Skype empresarial con Exchange 2013 o Exchange 2016. Debido a cambios en el soporte técnico de Exchange 2019, la integración de mensajería unificada de Exchange se subraya en favor del buzón de voz de nube y las características del operador automático de la nube.  Para obtener más información, vea [planear el servicio de buzón de voz en la nube](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) y el [plan de Skype empresarial Server y de la migración de Exchange Server](../../../sfbhybrid/hybrid/plan-um-migration.md) .


Para que estas características se admitan en una implementación de mensajería unificada de Exchange local, debe estar ejecutando una de las siguientes opciones:

- Microsoft Exchange Server 2010 o Service Pack más reciente (solo para servidores de Skype empresarial 2015)
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016

> [!NOTE]
> La mensajería unificada de Exchange, tal como se conocía anteriormente, ya no está disponible en Skype empresarial Server 2019, que usa el sistema telefónico para grabar mensajes de voz y, a continuación, dejar la grabación en el buzón de Exchange de un usuario. Consulte [planear el servicio de buzón de voz en la nube](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) para obtener más información.

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>Características de la mensajería unificada integrada y de Skype empresarial Server

Skype empresarial Server, Enterprise Voice usa la infraestructura de mensajería unificada (UM) de Exchange para proporcionar contestación de llamadas, notificaciones de llamadas, acceso por voz (incluido el correo de voz) y servicios de operador automático.

- **Contestador automático**: el contestador automático recibe mensajes de voz en nombre de los usuarios que no están disponibles o cuyas llamadas no se responden. Permite reproducir un saludo personal, grabar un mensaje y enviar el mensaje a la cola para su entrega en el buzón del usuario, que se almacena en el servidor de buzones de correo de Exchange.

    Si el autor de la llamada deja un mensaje, el mensaje se trasfiere a la bandeja de entrada del usuario. Si decide no dejar un mensaje, se almacena una notificación de llamada perdida en el buzón del usuario. Los usuarios pueden acceder a sus bandejas de entrada mediante el cliente de mensajería y colaboración de Microsoft Outlook, Outlook Web Access, la tecnología Exchange ActiveSync o Outlook Voice Access. Se pueden mostrar el asunto y la prioridad de las llamadas de manera similar al correo electrónico.

- **Outlook Voice Access** Outlook Voice Access permite a un usuario de telefonía IP obtener acceso no solo al correo de voz, sino también a la bandeja de entrada de Exchange, que incluye el correo electrónico, el calendario y los contactos de una interfaz de telefonía. El número de acceso de suscriptor es asignado por un administrador de mensajería unificada de Exchange.

- **Operador automático** El operador automático es una característica de mensajería unificada de Exchange que se puede usar para configurar un número de teléfono que no pertenezca a los usuarios para que puedan comunicarse con los representantes de la empresa. En particular, proporciona una serie de mensajes de voz que ayudan a una persona que llama externa a navegar por un sistema de menús. La lista de opciones disponibles está configurada en el servidor de mensajería unificada de Exchange por el administrador de mensajería unificada de Exchange.

- **Servicios de fax** La mensajería unificada de Exchange incluye características de fax, que permiten a los usuarios recibir faxes entrantes en sus buzones de Exchange. Para obtener más información, consulte [mensajería unificada](https://go.microsoft.com/fwlink/p/?linkId=135652) en la documentación de Microsoft Exchange Server.

    > [!NOTE]
    > Los servicios de fax proporcionados por el servidor de mensajería unificada de Exchange no están disponibles en implementaciones de Skype empresarial Server que están integradas en Microsoft Exchange Server 2010, Exchange 2010 con el Service Pack más reciente, Exchange 2013 o Exchange 2016.

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>Componentes y topologías para mensajería unificada local en Skype empresarial Server

### <a name="exchange-server-components"></a>Componentes de Exchange Server

Para proporcionar las características y los servicios de mensajería unificada de Exchange descritos en [características de mensajería unificada integrada y de Skype empresarial Server](#features-of-integrated-unified-messaging-and-skype-for-business-server) a usuarios de voz empresarial de su organización, debe implementar un servidor de correo de Microsoft Exchange y un servidor de acceso de cliente, que aloje buzones de usuario y proporciona una única ubicación de almacenamiento para el correo electrónico y el correo de voz. La mensajería unificada de Exchange se ejecuta como un servicio en el buzón de Exchange y los servidores de acceso de cliente.

Para obtener más información sobre los componentes de mensajería unificada de Exchange en Microsoft Exchange Server 2010, consulte [implementación de mensajería unificada de Exchange local para proporcionar el correo de voz de vista previa de Lync Server 2013](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx) .

### <a name="supported-topologies"></a>Topologías admitidas

Puede implementar Skype empresarial Server y mensajería unificada de Exchange en el mismo bosque o en varios bosques. Si la implementación abarca varios bosques, debe realizar los pasos de integración de Exchange para cada bosque de mensajería unificada de Exchange. Además, debe configurar cada bosque de Microsoft Exchange para confiar en el bosque de Skype empresarial Server y en el bosque de Skype empresarial Server para confiar en cada bosque de mensajería unificada de Exchange. Además de esta confianza de bosque, la configuración de mensajería unificada de Exchange para todos los usuarios debe establecerse en los objetos de usuario del bosque de Skype empresarial Server.

Skype empresarial Server admite las siguientes topologías para la integración de mensajería unificada de Exchange:

- Bosque único

- Dominio único (es decir, un único bosque con un único dominio). Skype empresarial Server, Microsoft Exchange y todos los usuarios residen en el mismo dominio.

- Varios dominios (es decir, un dominio raíz con uno o más dominios secundarios). Skype empresarial Server y los servidores de Microsoft Exchange se implementan en diferentes dominios desde el dominio en el que se crean los usuarios. Los servidores de mensajería unificada de Exchange se pueden implementar en diferentes dominios del grupo de servidores de Skype empresarial que admiten.

- Varios bosques (es decir, un bosque de recursos). Skype empresarial Server se implementa en un único bosque y, a continuación, los usuarios se distribuyen entre varios bosques. Los atributos de mensajería unificada de Exchange de los usuarios deben replicarse en el bosque de Skype empresarial Server.

    > [!NOTE]
    > Exchange se puede implementar en varios bosques. Cada organización de Exchange puede proporcionar mensajería unificada de Exchange a sus usuarios, o la mensajería unificada de Exchange se puede implementar en el mismo bosque que Skype empresarial Server.

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>Directrices para integrar la mensajería unificada local y Skype empresarial Server

Los siguientes procedimientos recomendados e instrucciones debe tenerse en cuenta cuando implemente Telefonía IP empresarial:

> [!IMPORTANT]
> La mensajería unificada de Exchange (UM) solo admite IPv6 si también usa UCMA 4.

- Implementar un servidor de Skype empresarial Server Standard Edition o un grupo de servidores front-end.

- Colabore con los administradores de Exchange para confirmar las tareas que realizará cada uno y así garantizar una integración correcta y homogénea.

- Implemente los roles de servidor de buzón de Exchange en cada bosque de mensajería unificada (UM) de Exchange donde desee habilitar usuarios para la mensajería unificada de Exchange. Para obtener más información sobre la instalación de los roles de servidor de Exchange, consulte la documentación de Microsoft Exchange Server.

    > [!IMPORTANT]
    > Cuando se instala mensajería unificada de Exchange (UM), se configura para usar un certificado autofirmado. El certificado autofirmado no permite que Skype empresarial Server y la mensajería unificada de Exchange confíen entre sí, razón por la cual es necesario solicitar un certificado independiente de una entidad emisora de certificados en la que confíen ambos servidores.

- Si Skype empresarial Server y mensajería unificada de Exchange se instalan en bosques diferentes, configure cada bosque de Exchange para que confíe en el bosque de Skype empresarial Server y en el bosque de Skype empresarial Server para confiar en cada uno de los bosques de Exchange. Además, establezca la configuración de mensajería unificada de Exchange en los objetos de usuario del bosque de Skype empresarial Server, generalmente mediante una secuencia de comandos o una herramienta entre bosques, como Identity Manager (ILM).

- Si es necesario, instale la Consola de administración de Exchange de modo que administre los servidores de mensajería unificada.

- Obtenga números de teléfono válidos para Outlook Voice Access y el operador automático.

- Si usa una versión de mensajería unificada de Exchange anterior a Microsoft Exchange Server 2010 Service Pack 1 (SP1), los nombres de coordenadas de los planes de marcado de URI del SIP de mensajería unificada de Exchange y los planes de marcado de voz de empresa.

### <a name="deploying-redundant-exchange-um-servers"></a>Implementación de servidores redundantes de mensajería unificada de Exchange

> [!IMPORTANT]
> Se recomienda implementar un mínimo de dos servidores en los que se ejecuten los servicios de mensajería unificada de Exchange para cada plan de marcado de URI del SIP de Exchange que configure para su organización. Además de ofrecer más capacidad, implementar servidores redundantes también proporciona una alta disponibilidad. En el caso de que se produzca un error de servidor, se puede configurar Skype empresarial Server para que realice la conmutación por error a otro servidor.

Los siguientes ejemplos de configuraciones ofrecen resistencia a la mensajería unificada de Exchange.

**Ejemplo 1: Resistencia de la mensajería unificada de Exchange**

![Diagrama de resistencia de Mensajería unificada de Exchange](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

En el Ejemplo 1, los servidores de mensajería unificada de Exchange 1 y 2 están habilitados en el centro de datos de Tukwila, y los servidores de mensajería unificada de Exchange 3 y 4 están habilitados en el centro de datos de Dublín. En el caso de que se produzca una interrupción de la mensajería unificada de Exchange en Tukwila, los registros de sistemas de nombre de dominio (DNS) A de los servidores 1 y 2 deben estar configurados para apuntar, respectivamente, a los servidores 3 y 4. En el caso de que se produzca una interrupción de la mensajería unificada de Exchange en Dublín, los registros DNS A de los servidores 3 y 4 deben estar configurados para apuntar, respectivamente, a los servidores 1 y 2.

> [!NOTE]
> Por ejemplo 1, también debe asignar uno de los siguientes certificados en cada servidor de mensajería unificada de Exchange: Use un certificado con un comodín en el nombre alternativo de sujeto (SAN) o ponga el nombre de dominio completo (FQDN) de cada uno de los cuatro servidores de MU de Exchange en la SAN.

**Ejemplo 2: Resistencia de la mensajería unificada de Exchange**

![Diagrama de resistencia de Mensajería unificada de Exchange](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

En el Ejemplo 2, en condiciones normales de funcionamiento, los servidores de mensajería unificada de Exchange 1 y 2 están habilitados en el centro de datos de Tukwila, y los servidores de mensajería unificada de Exchange 3 y 4 están habilitados en el centro de datos de Dublín. Los cuatro servidores están incluidos en el plan de marcado URI del SIP de los usuarios de Tukwila; sin embargo, los servidores 3 y 4 están deshabilitados. En el caso de que se produzca una interrupción de la mensajería unificada de Exchange en Tukwila, por ejemplo, los servidores 1 y 2 de mensajería unificada de Exchange deben deshabilitarse y los servidores 3 y 4 de mensajería unificada de Exchange deben habilitarse para que el tráfico de mensajería unificada de Exchange de Tukwila se enrute a los servidores de Dublín.

Para más información sobre cómo habilitar o deshabilitar la mensajería unificada en Exchange 2013, consulte integrar la mensajería unificada de [exchange 2013 con Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=265372). La información suministrada se aplica igualmente a Skype empresarial Server.

Para obtener más información sobre cómo habilitar o deshabilitar la mensajería unificada en Microsoft Exchange Server 2010, consulte:

- [Habilitar mensajería unificada en Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204418)

- [Deshabilitar la mensajería unificada en Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204416)

### <a name="exchange-server-2019"></a>Exchange Server 2019

La mensajería unificada de Exchange ya no está presente en Exchange 2019, si tiene Exchange 2019 y quiere una funcionalidad equivalente, tendrá que usar el servicio de buzón de voz de nube descrito en [plan servicio de buzón de voz en la nube](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md).


## <a name="see-also"></a>Vea también

[Información general sobre el proceso de implementación para integrar la mensajería unificada local y Skype Empresarial](deployment-overview.md)
