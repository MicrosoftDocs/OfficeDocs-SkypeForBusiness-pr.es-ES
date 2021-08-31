---
title: Planear la Exchange de mensajería unificada en Skype Empresarial
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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: 'Resumen: revise este tema al planear la integración de Skype Empresarial Server con Exchange 2013 o 2016.'
ms.openlocfilehash: bc378579d9d01fe783baa96d5869b3d340588b42
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "58725679"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>Planear la Exchange de mensajería unificada en Skype Empresarial

**Resumen:** Revise este tema mientras planea integrar Skype Empresarial Server con Exchange 2013 o 2016.

Skype Empresarial Server la integración con Exchange mensajería unificada (UM) para combinar la mensajería de voz y la mensajería de correo electrónico en una única infraestructura de mensajería. En Exchange, Exchange mensajería unificada (MU) es uno de los Exchange de servidor que puede instalar y configurar.

En Microsoft Exchange Server 2013 y 2016, Exchange mensajería unificada se ejecuta como servicio en un servidor Exchange buzón de correo. Para Skype Empresarial Server Telefonía IP empresarial, la mensajería unificada combina la mensajería de voz y la mensajería de correo electrónico en un único almacén al que los usuarios pueden acceder desde un teléfono (Outlook acceso de voz) o un equipo. La mensajería unificada y Skype Empresarial Server colaboran para proporcionar servicios de contestado de llamadas, acceso de voz Outlook y operadores automáticos a los usuarios de Telefonía IP empresarial.

> [!NOTE]
> Exchange La mensajería unificada permanece disponible Skype Empresarial Server 2019 al integrar Skype Empresarial 2019 con Exchange 2013 o Exchange 2016. Debido a los cambios en la compatibilidad en Exchange 2019, Exchange la integración de mensajería unificada se está haciendo hincapié en las características de Correo de voz en la nube y cloud Operador automático.  Vea [Plan Correo de voz en la nube service y](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) Plan for Skype Empresarial Server and Exchange Server [migration](../../../sfbhybrid/hybrid/plan-um-migration.md) para obtener más información.


Para que estas características sean compatibles con una implementación de mensajería unificada Exchange local, debe ejecutar una de las siguientes características:

- Microsoft Exchange Server 2010 o service pack más reciente (solo Skype Empresarial Server 2015)
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016

> [!NOTE]
> Exchange La mensajería unificada como se conocía anteriormente ya no está disponible en Skype Empresarial Server 2019, que usa Sistema telefónico para grabar mensajes de correo de voz y, a continuación, dejar la grabación en el buzón de correo de Exchange usuario. Vea [Plan Correo de voz en la nube service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) para obtener más información.

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>Características de mensajería unificada integrada y Skype Empresarial Server

Skype Empresarial Server, Telefonía IP empresarial usa la infraestructura de mensajería unificada (MU) de Exchange para proporcionar servicios de contestación de llamadas, notificación de llamadas, acceso de voz (incluido el correo de voz) y servicios de operador automático.

- **Contestando llamadas** El contestado de llamadas es la recepción de mensajes de voz en nombre de los usuarios cuyas llamadas no se responden o están ocupados. Incluye reproducir un saludo personal, grabar un mensaje y enviar el mensaje que se va a poner en cola para su entrega en el buzón del usuario, que se almacena en el servidor Exchange buzón de correo.

    Si el autor de la llamada deja un mensaje, el mensaje se trasfiere a la bandeja de entrada del usuario. Si decide no dejar un mensaje, se almacena una notificación de llamada perdida en el buzón del usuario. Los usuarios pueden acceder a sus bandejas de entrada mediante el cliente de mensajería y colaboración de Microsoft Outlook, Outlook Web Access, la tecnología Exchange ActiveSync o Outlook Voice Access. Se pueden mostrar el asunto y la prioridad de las llamadas de manera similar al correo electrónico.

- **Outlook Voice Access** Outlook Voice Access permite a un usuario de Telefonía IP empresarial acceder no solo al correo de voz, sino también Exchange la bandeja de entrada de Exchange, incluido el correo electrónico, el calendario y los contactos desde una interfaz de telefonía. Un administrador de mensajería unificada asigna el número de acceso Exchange suscriptor.

- **Operador automático** Operador automático es una Exchange de mensajería unificada que se puede usar para configurar un número de teléfono que los usuarios externos pueden marcar para llegar a los representantes de la compañía. Concretamente, proporciona una serie de indicadores de voz que ayudan al autor de una llamada externa a usar un sistema de menús. La lista de opciones disponibles está configurada en el Exchange de mensajería unificada por el Exchange de mensajería unificada.

- **Servicios de** fax Exchange mensajería unificada incluye características de fax, que permiten a los usuarios recibir faxes entrantes en sus buzones Exchange correo. Para obtener más información, consulte [Mensajería unificada](/previous-versions/office/exchange-server-2007/bb123911(v=exchg.80)) en la Microsoft Exchange Server documentación.

    > [!NOTE]
    > Los servicios de fax proporcionados por el servidor de mensajería unificada de Exchange no están disponibles en implementaciones de Skype Empresarial Server integradas con Microsoft Exchange Server 2010, Exchange 2010 con el service pack más reciente, Exchange 2013 o Exchange 2016.

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>Componentes y topologías para la mensajería unificada local en Skype Empresarial Server

### <a name="exchange-server-components"></a>Componentes de Exchange Server

Para proporcionar las características y servicios de mensajería unificada de Exchange que se describen en Características de mensajería unificada integrada y [Skype Empresarial Server](#features-of-integrated-unified-messaging-and-skype-for-business-server) para los usuarios de Telefonía IP empresarial de la organización, debe implementar un servidor de buzones de correo de Microsoft Exchange y un servidor de acceso de cliente, que hospeda buzones de usuario y proporciona una única ubicación de almacenamiento para correo electrónico y correo de voz. Exchange La mensajería unificada se ejecuta como un servicio en Exchange buzones de correo y servidores de acceso de cliente.

Para obtener más información Exchange componentes de mensajería unificada en Microsoft Exchange Server 2010, vea [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Preview Voice Mail](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail) .

### <a name="supported-topologies"></a>Topologías admitidas

Puede implementar Skype Empresarial Server y Exchange mensajería unificada (UM) en el mismo bosque o en varios bosques. Si la implementación abarca varios bosques, debe realizar los Exchange de integración de cada Exchange de mensajería unificada. Además, debe configurar cada bosque de Microsoft Exchange para que confíe en el bosque de Skype Empresarial Server y el bosque Skype Empresarial Server para confiar en cada bosque Exchange mensajería unificada. Además de esta confianza de bosque, la configuración Exchange de mensajería unificada de todos los usuarios debe establecerse en los objetos de usuario del Skype Empresarial Server bosque.

Skype Empresarial Server admite las siguientes topologías para la Exchange de mensajería unificada:

- Bosque único

- Dominio único (es decir, un único bosque con un único dominio). Skype Empresarial Server, Microsoft Exchange y los usuarios residen en el mismo dominio.

- Varios dominios (es decir, un dominio raíz con uno o más dominios secundarios). Skype Empresarial Server y los servidores Exchange microsoft se implementan en dominios distintos del dominio en el que se crean usuarios. Exchange Los servidores de mensajería unificada se pueden implementar en dominios diferentes del Skype Empresarial Server que admiten.

- Varios bosques (es decir, un bosque de recursos). Skype Empresarial Server se implementa en un solo bosque y, a continuación, los usuarios se distribuyen entre varios bosques. Los atributos de Exchange de mensajería unificada de los usuarios deben replicarse en el bosque Skype Empresarial Server usuario.

    > [!NOTE]
    > Exchange se puede implementar en varios bosques. Cada Exchange organización puede proporcionar Exchange mensajería unificada a sus usuarios o Exchange la mensajería unificada se puede implementar en el mismo bosque que Skype Empresarial Server.

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>Directrices para integrar la mensajería unificada local y Skype Empresarial Server

Las siguientes son directrices y procedimientos recomendados a tener en cuenta al implementar Telefonía IP empresarial:

> [!IMPORTANT]
> Exchange La mensajería unificada (MU) solo admite IPv6 si también usa UCMA 4.

- Implemente un Skype Empresarial Server Standard Edition o un grupo de servidores front-end.

- Colabore con los administradores de Exchange para confirmar las tareas que realizará cada uno y así garantizar una integración correcta y homogénea.

- Implemente los Exchange servidor de buzones de correo en cada bosque de mensajería unificada (MU) Exchange en el que desea habilitar a los usuarios para Exchange mensajería unificada. Para obtener más información acerca de Exchange roles de servidor, consulte la Microsoft Exchange Server web.

    > [!IMPORTANT]
    > Cuando Exchange mensajería unificada (UM), se configura para usar un certificado autofirmado. El certificado autofirmado no permite Skype Empresarial Server y Exchange mensajería unificada confiar entre sí, por lo que es necesario solicitar un certificado independiente de una entidad de certificación en la que ambos servidores confíen.

- Si Skype Empresarial Server y Exchange um están instalados en bosques diferentes, configure cada bosque de Exchange para que confíe en el bosque de Skype Empresarial Server y el bosque Skype Empresarial Server para que confíen en cada bosque Exchange. Además, establezca la configuración de mensajería unificada de Exchange de los usuarios en los objetos de usuario del bosque de Skype Empresarial Server, normalmente mediante un script o una herramienta entre bosques, como Identity Lifecycle Manager (ILM).

- Si es necesario, instale la Consola de administración de Exchange de modo que administre los servidores de mensajería unificada.

- Obtenga números de teléfono válidos para Outlook Voice Access y el operador automático.

- Si usa una versión de mensajería unificada de Exchange anterior a Microsoft Exchange Server 2010 Service Pack 1 (SP1 Exchange), los nombres de coordenadas de los planes de marcado URI de SIP de mensajería unificada y Telefonía IP empresarial de marcado.

### <a name="deploying-redundant-exchange-um-servers"></a>Implementación de servidores redundantes de mensajería unificada de Exchange

> [!IMPORTANT]
> Se recomienda implementar un mínimo de dos servidores en los que Exchange servicios de mensajería unificada se ejecuten para cada Exchange plan de marcado URI SIP de mensajería unificada que configure para su organización. Además de proporcionar capacidad ampliada, la implementación de servidores redundantes proporciona alta disponibilidad. En caso de error del servidor, Skype Empresarial Server puede configurarse para conmutar por error a otro servidor.

Los siguientes ejemplos de configuraciones ofrecen resistencia a la mensajería unificada de Exchange.

**Ejemplo 1: resistencia de la mensajería unificada de Exchange**

![Exchange Diagrama de resistencia de mensajería unificada.](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

En el Ejemplo 1, los servidores de mensajería unificada de Exchange 1 y 2 están habilitados en el centro de datos de Tukwila, y los servidores de mensajería unificada de Exchange 3 y 4 están habilitados en el centro de datos de Dublín. En caso de una interrupción de mensajería unificada de Exchange en Tukwila, los registros A del sistema de nombres de dominio (DNS) de los servidores 1 y 2 deben configurarse para que apunten a los servidores 3 y 4, respectivamente. En caso de una interrupción Exchange mensajería unificada en Dublín, los registros DNS A de los servidores 3 y 4 deben configurarse para que apunten a los servidores 1 y 2, respectivamente.

> [!NOTE]
> Por ejemplo 1, también debe asignar uno de los siguientes certificados en cada servidor de mensajería unificada de Exchange: use un certificado con un comodín en el Nombre alternativo de sujeto (SAN) o Ponga el nombre de dominio completo (FQDN) de cada uno de los cuatro servidores de mensajería unificada de Exchange en el SAN.

**Ejemplo 2: resistencia de la mensajería unificada de Exchange**

![Exchange Diagrama de resistencia de mensajería unificada.](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

En el Ejemplo 2, en condiciones normales de funcionamiento, los servidores de mensajería unificada de Exchange 1 y 2 están habilitados en el centro de datos de Tukwila, y los servidores de mensajería unificada de Exchange 3 y 4 están habilitados en el centro de datos de Dublín. Los cuatro servidores están incluidos en el plan de marcado URI del SIP de los usuarios de Tukwila; sin embargo, los servidores 3 y 4 están deshabilitados. En el caso de que se produzca una interrupción de la mensajería unificada de Exchange en Tukwila, por ejemplo, los servidores 1 y 2 de mensajería unificada de Exchange deben deshabilitarse y los servidores 3 y 4 de mensajería unificada de Exchange deben habilitarse para que el tráfico de mensajería unificada de Exchange de Tukwila se enrute a los servidores de Dublín.

Para obtener más información sobre cómo habilitar o deshabilitar la mensajería unificada en Exchange 2013, vea Integrar Exchange mensajería unificada [de 2013 con Lync Server](/exchange/checklist-integrate-exchange-2013-um-with-lync-server-exchange-2013-help). La información proporcionada se aplica igualmente a Skype Empresarial Server.

Para obtener más información sobre cómo habilitar o deshabilitar la mensajería unificada en Microsoft Exchange Server 2010, vea:

- [Habilitar la mensajería unificada en Exchange 2010](/previous-versions/office/exchange-server-2010/aa997908(v=exchg.141))

- [Deshabilitar la mensajería unificada en Exchange 2010](/previous-versions/office/exchange-server-2010/bb123529(v=exchg.141))

### <a name="exchange-server-2019"></a>Exchange Server 2019

Exchange La mensajería unificada ya no está presente en Exchange 2019, si tiene Exchange 2019 y desea una funcionalidad equivalente, deberá usar el servicio Correo de voz en la nube descrito en [Plan Correo de voz en la nube service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md).


## <a name="see-also"></a>Vea también

[Introducción al proceso de implementación para integrar la mensajería unificada local y Skype Empresarial](deployment-overview.md)