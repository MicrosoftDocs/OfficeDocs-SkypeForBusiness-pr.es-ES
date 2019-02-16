---
title: Planear la integración de la mensajería unificada de Exchange en Skype Empresarial
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: 'Resumen: Revise este tema cuando planee integrar Skype para Business Server con Exchange 2013 o 2016.'
ms.openlocfilehash: ee6e6bc81c4bd0b2291b7f4be7ceb13894d2aec2
ms.sourcegitcommit: 6d4b99de7233e91dbab4f08331dac4d88c51d9e4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2019
ms.locfileid: "30059190"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>Planear la integración de la mensajería unificada de Exchange en Skype Empresarial

**Resumen:** Revise este tema cuando planee integrar Skype para Business Server con Exchange 2013 o 2016.

Skype para Business Server admite la integración con Exchange mensajería unificada (UM) de la combinación de mensajería de voz y mensajería de correo electrónico en una sola infraestructura de mensajería. En Exchange, la mensajería unificada de Exchange (UM) es uno de varios roles de servidor de Exchange que se pueden instalar y configurar.

En Microsoft Exchange Server 2013 y 2016, mensajería unificada de Exchange se ejecuta como un servicio en un servidor de buzones de Exchange. Skype para las implementaciones empresariales Server Enterprise Voice, mensajería unificada combina mensajería de voz y correo electrónico de mensajería en un único almacén que pueden tener acceso los usuarios de un equipo o un teléfono (Outlook Voice Access). Mensajería unificada y Skype para Business Server funcionan conjuntamente para proporcionar el contestador automático, Outlook Voice Access y servicios de operador automático para los usuarios de Enterprise Voice.

> [!NOTE]
> Mensajería unificada de Exchange sigue estando disponible en Skype para Business Server 2019 al integrar Skype para la empresa 2019 con Exchange 2013 o 2016 de Exchange. Debido a los cambios en la compatibilidad en Exchange 2019, integración de mensajería unificada de Exchange se está desaprovisionamiento emphasised en favor de las características de correo de voz en la nube y operador automático de la nube.  Para obtener más información, vea [servicio de planeación de correo de voz en la nube](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) y [planeación de Skype para Business Server y la migración de Exchange Server](../../../sfbhybrid/hybrid/plan-um-migration.md) .


Para que estas características sean compatibles con una implementación local de mensajería unificada de Exchange, debe ejecutar uno de estos procedimientos:

- Microsoft Exchange Server 2010 o el último service pack (Skype para Business Server solo 2015)
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016
- Microsoft Exchange Server 2019 (Skype para Business Server 2019 sólo)

> [!NOTE]
> Mensajería unificada de Exchange como conocidos anteriormente ya no está disponible en Skype para Business Server 2019, que usa el sistema telefónico para registrar los mensajes de correo de voz y, a continuación, deje la grabación en el buzón de Exchange del usuario. Para obtener más información, vea [servicio de planeación de correo de voz en la nube](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) .

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>Características de mensajería unificada integrada y Skype para Business Server

Skype para Business Server, Enterprise Voice usa la infraestructura de mensajería unificada de Exchange (UM) para proporcionar el contestador automático, notificación de llamada, acceso de voz (incluido el correo de voz) y servicios de operador automático.

- **Contestador automático**: el contestador automático recibe mensajes de voz en nombre de los usuarios que no están disponibles o cuyas llamadas no se responden. Permite reproducir un saludo personal, grabar un mensaje y enviar el mensaje a la cola para su entrega en el buzón del usuario, que se almacena en el servidor de buzones de correo de Exchange.

    Si el autor de la llamada deja un mensaje, el mensaje se trasfiere a la bandeja de entrada del usuario. Si decide no dejar un mensaje, se almacena una notificación de llamada perdida en el buzón del usuario. Los usuarios pueden acceder a sus bandejas de entrada mediante el cliente de mensajería y colaboración de Microsoft Outlook, Outlook Web Access, la tecnología Exchange ActiveSync o Outlook Voice Access. Se pueden mostrar el asunto y la prioridad de las llamadas de manera similar al correo electrónico.

- **Outlook Voice Access** Outlook Voice Access permite a un usuario de Enterprise Voice tener acceso a correo de voz no sólo, sino también la Bandeja de entrada de Exchange, incluido el correo electrónico, calendario y contactos desde una interfaz de telefonía. Se asigna el número de acceso de suscriptor por un administrador de mensajería unificada de Exchange.

- **Operador automático** Operador automático es una característica de mensajería unificada de Exchange que se puede usar para configurar un número de teléfono que los usuarios externos puede marcar para llegar a los representantes de la empresa. En concreto, proporciona una serie de mensajes de voz que ayudan a un autor de la llamada externa a navegar por un sistema de menús. Se configura la lista de opciones disponibles en el servidor de mensajería unificada de Exchange por el Administrador de la mensajería unificada de Exchange.

- **Servicios de fax** Mensajería unificada de Exchange incluye características de fax, que permiten a los usuarios recibir faxes entrantes en sus buzones de Exchange. Para más información, vea [Mensajería unificada](https://go.microsoft.com/fwlink/p/?linkId=135652) en la documentación de Microsoft Exchange Server.

    > [!NOTE]
    > Los servicios de fax proporcionados por el servidor de mensajería unificada de Exchange no están disponibles en Skype para las implementaciones de Business Server que se integran con Microsoft Exchange Server 2010, Exchange 2010 con el último service pack, Exchange 2013 o 2016 de Exchange.

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>Componentes y topologías para local mensajería unificada en Skype para Business Server

### <a name="exchange-server-components"></a>Componentes de Exchange Server

Para proporcionar las características de mensajería unificada de Exchange y servicios que se describen en [las características de mensajería unificada y Skype para Business Server integrados](#features-of-integrated-unified-messaging-and-skype-for-business-server) a los usuarios de Enterprise Voice en su organización, debe implementar un servidor de buzones de Microsoft Exchange y el acceso de cliente servidor que hospeda los buzones de usuario y proporciona una única ubicación de almacenamiento para correo electrónico y correo de voz. Mensajería unificada de Exchange se ejecuta como un servicio en servidores de buzón de Exchange y de acceso de cliente.

Para obtener información detallada acerca de los componentes de mensajería unificada de Exchange en Microsoft Exchange Server 2010, vea [Implementación local mensajería unificada de Exchange para proporcionar correo de voz de Lync Server 2013 Preview](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx) .

### <a name="supported-topologies"></a>Topologías admitidas

Puede implementar Skype para Business Server y Exchange mensajería unificada (UM) en el mismo bosque o varios bosques. Si la implementación abarca varios bosques, debe realizar los pasos de integración de Exchange para cada bosque de mensajería unificada de Exchange. Además, debe configurar cada bosque de Microsoft Exchange para que confíe en el Skype para bosque Business Server y la Skype para bosque Business Server para que confíe en cada bosque de mensajería unificada de Exchange. Además de esta relación de confianza de bosque, la configuración de mensajería unificada de Exchange para todos los usuarios debe establecerse en los objetos de usuario en el Skype para bosque Business Server.

Skype para Business Server admite las siguientes topologías para la integración de mensajería unificada de Exchange:

- Bosque único

- Dominio único (es decir, un único bosque con un único dominio). Skype para Business Server, Microsoft Exchange y los usuarios residen en el mismo dominio.

- Varios dominios (es decir, un dominio raíz con uno o más dominios secundarios). Skype para Business Server y los servidores de Microsoft Exchange se implementan en diferentes dominios desde el dominio donde se crean los usuarios. Servidores de mensajería unificada de Exchange pueden implementarse en diferentes dominios desde el Skype para grupo de servidores de negocio que admiten.

- Varios bosques (es decir, un bosque de recursos). Skype para Business Server se implementa en un solo bosque y, a continuación, se distribuyen a los usuarios en varios bosques. Atributos de los usuarios para mensajería unificada de Exchange deben replicarse a través de a la Skype para bosque Business Server.

    > [!NOTE]
    > Exchange se puede implementar en varios bosques. Cada organización de Exchange puede proporcionar mensajería unificada de Exchange a sus usuarios, o mensajería unificada de Exchange puede implementarse en el mismo bosque que Skype para Business Server.

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>Instrucciones para la integración local mensajería unificada y Skype para Business Server

Los siguientes procedimientos recomendados e instrucciones debe tenerse en cuenta cuando implemente Telefonía IP empresarial:

> [!IMPORTANT]
> Mensajería unificada de Exchange (UM) es compatible con IPv6 sólo si también está usando UCMA 4.

- Implementar un Skype para Business Server Standard Edition o un grupo de servidores Front-End.

- Colabore con los administradores de Exchange para confirmar las tareas que realizará cada uno y así garantizar una integración correcta y homogénea.

- Implementar las funciones de servidor de buzón de Exchange en cada bosque de mensajería unificada de Exchange (UM) donde desea permitir a que los usuarios de mensajería unificada de Exchange. Para obtener información detallada acerca de cómo instalar roles de servidor de Exchange, consulte la documentación de Microsoft Exchange Server 2013.

    > [!IMPORTANT]
    > Cuando se instala mensajería unificada de Exchange (UM), está configurado para usar un certificado autofirmado. El certificado autofirmado no habilita Skype para Business Server y mensajería unificada de Exchange confíen entre sí, que es la razón por la que es necesario solicitar un certificado independiente de una entidad de certificación que ambos servidores de confianza.

- Si Skype para Business Server y la mensajería unificada de Exchange se instala en bosques distintos, configure cada bosque de Exchange para que confíe en el Skype para bosque Business Server y la Skype para bosque Business Server para que confíe en cada bosque de Exchange. También, establecer la configuración mensajería unificada de Exchange de los usuarios en los objetos de usuario en el Skype para el bosque de Business Server, normalmente mediante una secuencia de comandos o una herramienta de entre bosques, como Identity Lifecycle Manager (ILM).

- Si es necesario, instale la Consola de administración de Exchange de modo que administre los servidores de mensajería unificada.

- Obtenga números de teléfono válidos para Outlook Voice Access y el operador automático.

- Si está utilizando una versión de mensajería unificada de Exchange anterior a Microsoft Exchange Server 2010 Service Pack 1 (SP1), los nombres de coordenadas para Exchange UM URI del SIP planes de marcado y los planes de marcado de Enterprise Voice.

### <a name="deploying-redundant-exchange-um-servers"></a>Implementación de servidores redundantes de mensajería unificada de Exchange

> [!IMPORTANT]
> Se recomienda que implemente un mínimo de dos servidores en la mensajería unificada de Exchange services se está ejecutando para cada plan de marcado de Exchange UM URI del SIP que configura para la organización. Además de ofrecer más capacidad, implementar servidores redundantes también proporciona una alta disponibilidad. En el caso de un error del servidor, Skype para Business Server puede configurarse para conmutar por error a otro servidor.

Los siguientes ejemplos de configuraciones ofrecen resistencia a la mensajería unificada de Exchange.

**Ejemplo 1: Resistencia de la mensajería unificada de Exchange**

![Diagrama de resistencia de Mensajería unificada de Exchange](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

En el Ejemplo 1, los servidores de mensajería unificada de Exchange 1 y 2 están habilitados en el centro de datos de Tukwila, y los servidores de mensajería unificada de Exchange 3 y 4 están habilitados en el centro de datos de Dublín. En el caso de que se produzca una interrupción de la mensajería unificada de Exchange en Tukwila, los registros de sistemas de nombre de dominio (DNS) A de los servidores 1 y 2 deben estar configurados para apuntar, respectivamente, a los servidores 3 y 4. En el caso de que se produzca una interrupción de la mensajería unificada de Exchange en Dublín, los registros DNS A de los servidores 3 y 4 deben estar configurados para apuntar, respectivamente, a los servidores 1 y 2.

> [!NOTE]
> Por ejemplo 1, debe asignar también uno de los siguientes certificados en cada servidor de mensajería unificada de Exchange: usar un certificado con un carácter comodín en el nombre alternativo de sujeto (SAN) o coloque el nombre de dominio completo (FQDN) de cada uno de los cuatro servidores mensajería unificada de Exchange en el SAN.

**Ejemplo 2: Resistencia de la mensajería unificada de Exchange**

![Diagrama de resistencia de Mensajería unificada de Exchange](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

En el Ejemplo 2, en condiciones normales de funcionamiento, los servidores de mensajería unificada de Exchange 1 y 2 están habilitados en el centro de datos de Tukwila, y los servidores de mensajería unificada de Exchange 3 y 4 están habilitados en el centro de datos de Dublín. Los cuatro servidores están incluidos en el plan de marcado URI del SIP de los usuarios de Tukwila; sin embargo, los servidores 3 y 4 están deshabilitados. En el caso de que se produzca una interrupción de la mensajería unificada de Exchange en Tukwila, por ejemplo, los servidores 1 y 2 de mensajería unificada de Exchange deben deshabilitarse y los servidores 3 y 4 de mensajería unificada de Exchange deben habilitarse para que el tráfico de mensajería unificada de Exchange de Tukwila se enrute a los servidores de Dublín.

Para obtener información detallada acerca de cómo habilitar o deshabilitar la mensajería unificada en Exchange 2013, consulte [Integrate Exchange 2013 UM con Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=265372). La información proporcionada se aplica igualmente a Skype para Business Server.

Para obtener información detallada acerca de cómo habilitar o deshabilitar la mensajería unificada en Microsoft Exchange Server 2010, consulte:

- [Habilitar mensajería unificada en Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204418)

- [Deshabilitar mensajería unificada en Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204416)

### <a name="exchange-server-2019"></a>Exchange Server 2019

Mensajería unificada de Exchange ya no está presente en Exchange 2019, si dispone de Exchange 2019 y desea que necesita usar el servicio de correo de voz en la nube que se describen en el [servicio de correo de voz de la nube de planeación de](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)una funcionalidad equivalente.


## <a name="see-also"></a>Vea también

[Información general sobre el proceso de implementación para integrar la mensajería unificada local y Skype Empresarial](deployment-overview.md)