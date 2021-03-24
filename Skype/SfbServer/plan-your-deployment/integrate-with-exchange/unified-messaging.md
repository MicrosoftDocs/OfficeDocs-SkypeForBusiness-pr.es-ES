---
title: Planear la integración de mensajería unificada de Exchange en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumen: revise este tema al planear la integración de Skype Empresarial Server con Exchange 2013 o 2016.'
ms.openlocfilehash: 95df4d0fa9d2a57385c5dd61c95bc07c07a8fa7c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096666"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>Planear la integración de mensajería unificada de Exchange en Skype Empresarial

**Resumen:** Revise este tema al planear la integración de Skype Empresarial Server con Exchange 2013 o 2016.

Skype Empresarial Server admite la integración con la mensajería unificada (UM) de Exchange para combinar la mensajería de voz y la mensajería de correo electrónico en una única infraestructura de mensajería. En Exchange, la mensajería unificada (UM) de Exchange es uno de los varios roles de servidor de Exchange que puede instalar y configurar.

En Microsoft Exchange Server 2013 y 2016, la mensajería unificada de Exchange se ejecuta como servicio en un servidor de buzones de Exchange. Para las implementaciones Telefonía IP empresarial de Skype Empresarial Server, la mensajería unificada combina la mensajería de voz y la mensajería de correo electrónico en un único almacén al que los usuarios pueden acceder desde un teléfono (Outlook Voice Access) o un equipo. La mensajería unificada y Skype Empresarial Server colaboran para proporcionar servicios de contestación de llamadas, Outlook Voice Access y operadores automáticos a los usuarios de Telefonía IP empresarial.

> [!NOTE]
> La mensajería unificada de Exchange permanece disponible en Skype Empresarial Server 2019 al integrar Skype Empresarial 2019 con Exchange 2013 o Exchange 2016. Debido a los cambios en la compatibilidad con Exchange 2019, la integración de mensajería unificada de Exchange se está desmarcando a favor del correo de voz en la nube y las características Operador automático nube.  Vea [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) and Plan for Skype for Business Server y Exchange Server [migration](../../../sfbhybrid/hybrid/plan-um-migration.md) para obtener más información.


Para que estas características sean compatibles con una implementación de mensajería unificada de Exchange local, debe ejecutar una de las siguientes características:

- Microsoft Exchange Server 2010 o service pack más reciente (solo Skype Empresarial Server 2015)
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016

> [!NOTE]
> La mensajería unificada de Exchange como se conocía anteriormente ya no está disponible en Skype Empresarial Server 2019, que usa sistema telefónico para grabar mensajes de correo de voz y, a continuación, dejar la grabación en el buzón de Exchange de un usuario. Consulte [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) para obtener más información.

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>Características de mensajería unificada integrada y Skype Empresarial Server

Skype Empresarial Server, Telefonía IP empresarial usa la infraestructura de mensajería unificada (MU) de Exchange para proporcionar servicios de contestación de llamadas, notificación de llamadas, acceso de voz (incluido el correo de voz) y servicios de operador automático.

- **Contestando llamadas** El contestado de llamadas es la recepción de mensajes de voz en nombre de los usuarios cuyas llamadas no se responden o están ocupados. Incluye reproducir un saludo personal, grabar un mensaje y enviar el mensaje que se va a poner en cola para su entrega en el buzón del usuario, que se almacena en el servidor de buzones de Exchange.

    Si el autor de la llamada deja un mensaje, el mensaje se trasfiere a la bandeja de entrada del usuario. Si decide no dejar un mensaje, se almacena una notificación de llamada perdida en el buzón del usuario. Los usuarios pueden acceder a sus bandejas de entrada mediante el cliente de mensajería y colaboración de Microsoft Outlook, Outlook Web Access, la tecnología Exchange ActiveSync o Outlook Voice Access. Se pueden mostrar el asunto y la prioridad de las llamadas de manera similar al correo electrónico.

- **Outlook Voice Access** Outlook Voice Access permite a un usuario de Telefonía IP empresarial acceder no solo al correo de voz, sino también a la bandeja de entrada de Exchange, incluido el correo electrónico, el calendario y los contactos desde una interfaz de telefonía. Un administrador de mensajería unificada de Exchange asigna el número de acceso de suscriptor.

- **Operador automático** Operador automático es una característica de mensajería unificada de Exchange que se puede usar para configurar un número de teléfono que los usuarios externos pueden marcar para llegar a los representantes de la compañía. Concretamente, proporciona una serie de indicadores de voz que ayudan al autor de una llamada externa a usar un sistema de menús. El administrador de mensajería unificada de Exchange configura la lista de opciones disponibles en el servidor de mensajería unificada de Exchange.

- **Servicios de fax** La mensajería unificada de Exchange incluye características de fax, que permiten a los usuarios recibir faxes entrantes en sus buzones de Exchange. Para obtener más información, consulte [Mensajería unificada](/previous-versions/office/exchange-server-2007/bb123911(v=exchg.80)) en la Microsoft Exchange Server documentación.

    > [!NOTE]
    > Los servicios de fax proporcionados por el servidor de mensajería unificada de Exchange no están disponibles en implementaciones de Skype Empresarial Server integradas con Microsoft Exchange Server 2010, Exchange 2010 con el service pack más reciente, Exchange 2013 o Exchange 2016.

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>Componentes y topologías para la mensajería unificada local en Skype Empresarial Server

### <a name="exchange-server-components"></a>Componentes de Exchange Server

Para proporcionar las características y servicios de mensajería unificada de Exchange que se describen en Características de mensajería unificada integrada y Skype Empresarial [Server](#features-of-integrated-unified-messaging-and-skype-for-business-server) Telefonía IP empresarial los usuarios de su organización, debe implementar un servidor de buzones de Microsoft Exchange y un servidor de acceso de cliente, que hospeda buzones de usuario y proporciona una única ubicación de almacenamiento para correo electrónico y correo de voz. La mensajería unificada de Exchange se ejecuta como un servicio en los servidores de acceso de cliente y buzón de Exchange.

Para obtener más información acerca de los componentes de mensajería unificada de Exchange en Microsoft Exchange Server 2010, vea [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Preview Voice Mail](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail) .

### <a name="supported-topologies"></a>Topologías admitidas

Puede implementar Skype Empresarial Server y mensajería unificada de Exchange (UM) en el mismo bosque o en varios bosques. Si la implementación abarca varios bosques, debe realizar los pasos de integración de Exchange para cada bosque de mensajería unificada de Exchange. Además, debe configurar cada bosque de Microsoft Exchange para que confíe en el bosque de Skype Empresarial Server y en el bosque de Skype Empresarial Server para que confíe en cada bosque de mensajería unificada de Exchange. Además de esta confianza de bosque, la configuración de mensajería unificada de Exchange para todos los usuarios debe establecerse en los objetos de usuario del bosque de Skype Empresarial Server.

Skype Empresarial Server admite las siguientes topologías para la integración de mensajería unificada de Exchange:

- Bosque único

- Dominio único (es decir, un único bosque con un único dominio). Skype Empresarial Server, Microsoft Exchange y los usuarios residen en el mismo dominio.

- Varios dominios (es decir, un dominio raíz con uno o más dominios secundarios). Skype Empresarial Server y los servidores de Microsoft Exchange se implementan en dominios diferentes del dominio donde se crean usuarios. Los servidores de mensajería unificada de Exchange se pueden implementar en dominios diferentes del grupo de servidores de Skype Empresarial Server que admiten.

- Varios bosques (es decir, un bosque de recursos). Skype Empresarial Server se implementa en un solo bosque y, a continuación, los usuarios se distribuyen entre varios bosques. Los atributos de mensajería unificada de Exchange de los usuarios deben replicarse en el bosque de Skype Empresarial Server.

    > [!NOTE]
    > Exchange se puede implementar en varios bosques. Cada organización de Exchange puede proporcionar mensajería unificada de Exchange a sus usuarios o la mensajería unificada de Exchange se puede implementar en el mismo bosque que Skype Empresarial Server.

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>Directrices para integrar la mensajería unificada local y Skype Empresarial Server

Las siguientes son instrucciones y procedimientos recomendados a tener en cuenta al implementar Telefonía IP empresarial:

> [!IMPORTANT]
> La mensajería unificada (UM) de Exchange solo admite IPv6 si también usa UCMA 4.

- Implementar un servidor Standard Edition de Skype Empresarial Server o un grupo de servidores front-end.

- Colabore con los administradores de Exchange para confirmar las tareas que realizará cada uno y así garantizar una integración correcta y homogénea.

- Implemente los roles de servidor buzón de Exchange en cada bosque de mensajería unificada de Exchange donde desee habilitar usuarios para mensajería unificada de Exchange. Para obtener más información acerca de la instalación de roles de servidor de Exchange, consulte Microsoft Exchange Server documentación.

    > [!IMPORTANT]
    > Cuando se instala la mensajería unificada (MU) de Exchange, se configura para usar un certificado autofirmado. El certificado autofirmado no permite que Skype Empresarial Server y mensajería unificada de Exchange confíen entre sí, por lo que es necesario solicitar un certificado independiente de una entidad de certificación en la que ambos servidores confíen.

- Si Skype Empresarial Server y mensajería unificada de Exchange están instalados en bosques diferentes, configure cada bosque de Exchange para que confíe en el bosque de Skype Empresarial Server y el bosque de Skype Empresarial Server para que confíe en cada bosque de Exchange. Además, establezca la configuración de mensajería unificada de Exchange de los usuarios en los objetos de usuario del bosque de Skype Empresarial Server, normalmente mediante un script o una herramienta entre bosques, como Identity Lifecycle Manager (ILM).

- Si es necesario, instale la Consola de administración de Exchange de modo que administre los servidores de mensajería unificada.

- Obtenga números de teléfono válidos para Outlook Voice Access y el operador automático.

- Si usa una versión de mensajería unificada de Exchange anterior a Microsoft Exchange Server 2010 Service Pack 1 (SP1), los nombres de coordenadas de los planes de marcado URI sip de mensajería unificada de Exchange y Telefonía IP empresarial de marcado.

### <a name="deploying-redundant-exchange-um-servers"></a>Implementación de servidores redundantes de mensajería unificada de Exchange

> [!IMPORTANT]
> Se recomienda implementar un mínimo de dos servidores en los que se ejecuten los servicios de mensajería unificada de Exchange para cada plan de marcado uri sip de mensajería unificada de Exchange que configure para la organización. Además de proporcionar capacidad ampliada, la implementación de servidores redundantes proporciona alta disponibilidad. En caso de error del servidor, Skype Empresarial Server puede configurarse para conmutar por error a otro servidor.

Los siguientes ejemplos de configuraciones ofrecen resistencia a la mensajería unificada de Exchange.

**Ejemplo 1: resistencia de la mensajería unificada de Exchange**

![Diagrama de resistencia de mensajería unificada de Exchange](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

En el Ejemplo 1, los servidores de mensajería unificada de Exchange 1 y 2 están habilitados en el centro de datos de Tukwila, y los servidores de mensajería unificada de Exchange 3 y 4 están habilitados en el centro de datos de Dublín. En caso de una interrupción de mensajería unificada de Exchange en Tukwila, los registros A del sistema de nombres de dominio (DNS) para los servidores 1 y 2 deben configurarse para que apunten a los servidores 3 y 4, respectivamente. En caso de una interrupción de mensajería unificada de Exchange en Dublín, los registros DNS A de los servidores 3 y 4 deben configurarse para que apunten a los servidores 1 y 2, respectivamente.

> [!NOTE]
> Por ejemplo 1, también debe asignar uno de los siguientes certificados en cada servidor de mensajería unificada de Exchange: use un certificado con un comodín en el nombre alternativo de sujeto (SAN) o coloque el nombre de dominio completo (FQDN) de cada uno de los cuatro servidores de mensajería unificada de Exchange en el SAN.

**Ejemplo 2: resistencia de la mensajería unificada de Exchange**

![Diagrama de resistencia de mensajería unificada de Exchange](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

En el Ejemplo 2, en condiciones normales de funcionamiento, los servidores de mensajería unificada de Exchange 1 y 2 están habilitados en el centro de datos de Tukwila, y los servidores de mensajería unificada de Exchange 3 y 4 están habilitados en el centro de datos de Dublín. Los cuatro servidores están incluidos en el plan de marcado URI del SIP de los usuarios de Tukwila; sin embargo, los servidores 3 y 4 están deshabilitados. En el caso de que se produzca una interrupción de la mensajería unificada de Exchange en Tukwila, por ejemplo, los servidores 1 y 2 de mensajería unificada de Exchange deben deshabilitarse y los servidores 3 y 4 de mensajería unificada de Exchange deben habilitarse para que el tráfico de mensajería unificada de Exchange de Tukwila se enrute a los servidores de Dublín.

Para obtener más información sobre cómo habilitar o deshabilitar la mensajería unificada en Exchange 2013, vea Integrar la mensajería unificada de  [Exchange 2013 con Lync Server](/exchange/checklist-integrate-exchange-2013-um-with-lync-server-exchange-2013-help). La información proporcionada se aplica igualmente a Skype Empresarial Server.

Para obtener más información sobre cómo habilitar o deshabilitar la mensajería unificada en Microsoft Exchange Server 2010, vea:

- [Habilitar la mensajería unificada en Exchange 2010](/previous-versions/office/exchange-server-2010/aa997908(v=exchg.141))

- [Deshabilitar la mensajería unificada en Exchange 2010](/previous-versions/office/exchange-server-2010/bb123529(v=exchg.141))

### <a name="exchange-server-2019"></a>Exchange Server 2019

La mensajería unificada de Exchange ya no está presente en Exchange 2019, si tiene Exchange 2019 y desea una funcionalidad equivalente, deberá usar el servicio de correo de voz en la nube descrito en [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md).


## <a name="see-also"></a>Ver también

[Introducción al proceso de implementación para integrar la mensajería unificada local y Skype Empresarial](deployment-overview.md)