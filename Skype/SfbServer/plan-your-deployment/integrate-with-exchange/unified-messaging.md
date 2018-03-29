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
description: 'Resumen: Revisar este tema mientras se planea integrar Skype para Business Server 2015 con Exchange de 2013.'
ms.openlocfilehash: 1a1ea968f9feb14c0a7b0d69c13ad273a18a53f5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>Planear la integración de la mensajería unificada de Exchange en Skype Empresarial
 
**Resumen:** Revise este tema mientras se planea integrar Skype para Business Server 2015 con Exchange de 2013.
  
Skype para el año 2015 de Business Server admite la integración con Exchange Unified Messaging (UM) para combinar la mensajería de voz y mensajería de correo electrónico en una única infraestructura de mensajería. En Exchange, Exchange Unified Messaging (UM) es una de varias funciones de servidor de Exchange que puede instalar y configurar. 
  
En Microsoft Exchange Server 2013, mensajería unificada de Exchange se ejecuta como un servicio en un servidor de buzones de Exchange. Skype para implementaciones de Telefonía IP empresarial de Business Server 2015, mensajería unificada combina mensajería de voz y correo electrónico de mensajería en un único almacén en el que los usuarios pueden acceder desde un equipo o un teléfono (Outlook Voice Access). De mensajería unificada y Skype para Business Server 2015 colaboran para proporcionar servicios de operador automático, Outlook Voice Access y responder a la llamada a los usuarios de Telefonía IP empresarial.
  
Para obtener más información acerca de los cambios de arquitectura en Microsoft Exchange Server 2013, vea [Cambios de arquitectura de voz](https://go.microsoft.com/fwlink/p/?LinkId=266730) en la documentación de Microsoft Exchange Server 2013.
  
Para que estas características se admiten en una implementación local de mensajería unificada de Exchange, debe ejecutar uno de estos procedimientos:
  
- Microsoft Exchange Server 2010 o el service pack más reciente
    
- Microsoft Exchange Server 2013
    
-  Microsoft Exchange Server 2016
    
## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server-2015"></a>Características de la mensajería unificada integrada y Skype Empresarial Server 2015

Skype para Business Server 2015, Telefonía IP empresarial utiliza la infraestructura de Exchange Unified Messaging (UM) para proporcionar contestación de llamadas, notificación de llamada, acceso de voz (incluido el correo de voz) y servicios de operador automático.
  
- **Contestador automático**: el contestador automático recibe mensajes de voz en nombre de los usuarios que no están disponibles o cuyas llamadas no se responden. Permite reproducir un saludo personal, grabar un mensaje y enviar el mensaje a la cola para su entrega en el buzón del usuario, que se almacena en el servidor de buzones de correo de Exchange.
    
    Si el autor de la llamada deja un mensaje, el mensaje se trasfiere a la bandeja de entrada del usuario. Si decide no dejar un mensaje, se almacena una notificación de llamada perdida en el buzón del usuario. Los usuarios pueden acceder a sus bandejas de entrada mediante el cliente de mensajería y colaboración de Microsoft Outlook, Outlook Web Access, la tecnología Exchange ActiveSync o Outlook Voice Access. Se pueden mostrar el asunto y la prioridad de las llamadas de manera similar al correo electrónico.
    
- **Outlook Voice Access** Outlook Voice Access permite a un usuario de Telefonía IP empresarial tener acceso a correo de voz no sólo, sino también a la Bandeja de entrada de Exchange, incluyendo correo electrónico, calendario y contactos desde una interfaz de telefonía. El número de acceso de suscriptor es asignado por un administrador de mensajería unificada de Exchange.
    
- **Operador automático** Operador automático es una característica de mensajería unificada de Exchange que puede utilizarse para configurar un número de teléfono que puede marcar para llegar a los representantes de la sociedad de usuarios externos. En particular, proporciona una serie de mensajes de voz que ayudan a un llamador externo al desplazarse en un sistema de menús. La lista de opciones disponibles está configurada en el servidor de mensajería unificada de Exchange, el Administrador de mensajería unificada de Exchange.
    
- **Servicios de fax** Mensajería unificada de Exchange incluye funciones de fax, que permiten a los usuarios recibir faxes entrantes en sus buzones de Exchange. Para obtener información detallada, vea [Mensajería unificada](https://go.microsoft.com/fwlink/p/?linkId=135652) en la documentación de Microsoft Exchange Server.
    
    > [!NOTE]
    > Servicios de fax proporcionados por el servidor de mensajería unificada de Exchange no están disponibles en Skype para implementaciones de Business Server que se integran con Microsoft Exchange Server 2010, Exchange 2010 con el último service pack o intercambio de 2013. 
  
## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server-2015"></a>Componentes y topologías para mensajería unificada local en Skype Empresarial Server 2015

### <a name="exchange-server-components"></a>Componentes de Exchange Server

Para proporcionar las características de mensajería unificada de Exchange y los servicios descritos en [características de integrado mensajería unificada y Lync Server 2013](http://technet.microsoft.com/library/094f549d-fccc-43ab-9f39-6ddd18130915.aspx) a los usuarios de Telefonía IP empresarial en su organización, debe implementar un servidor de buzones de Microsoft Exchange y el servidor acceso de cliente, que aloja los buzones de usuario y proporciona una única ubicación de almacenamiento para correo electrónico y correo de voz. Mensajería unificada de Exchange se ejecuta como un servicio en los servidores de buzón de Exchange y de acceso de cliente.
  
Para obtener más información acerca de los componentes de mensajería unificada de Exchange en Microsoft Exchange Server 2010, vea [Implementación local mensajería unificada de Exchange para proporcionar correo de voz de vista previa de Lync Server 2013](http://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx) en la documentación de implementación.
  
### <a name="supported-topologies"></a>Topologías admitidas

Puede implementar Skype para Business Server 2015 y Exchange Unified Messaging (UM) en el mismo bosque o varios bosques. Si la implementación abarca varios bosques, debe realizar los pasos de la integración de Exchange en cada bosque de mensajería unificada de Exchange. Además, debe configurar cada bosque de Microsoft Exchange para que confíe en el Skype para el bosque Business Server 2015 y el Skype para Business Server 2015 bosque para confiar en cada bosque de mensajería unificada de Exchange. Además de esta confianza de bosque, la configuración de mensajería unificada de Exchange para todos los usuarios debe establecerse en los objetos de usuario en el Skype para el bosque Business Server 2015. 
  
Skype para el año 2015 de Business Server admite las siguientes topologías para la integración de mensajería unificada de Exchange:
  
- Bosque único
    
- Dominio único (es decir, un único bosque con un único dominio). Skype para Business Server 2015, Microsoft Exchange y los usuarios residen en el mismo dominio.
    
- Varios dominios (es decir, un dominio raíz con uno o más dominios secundarios). Skype para Business Server 2015 y servidores de Microsoft Exchange se implementan en dominios distintos del dominio en el que crear los usuarios. Servidores de mensajería unificada de Exchange pueden implementarse en diferentes dominios desde el Skype para grupo Business Server 2015 que admiten.
    
- Varios bosques (es decir, un bosque de recursos). Skype para el año 2015 de Business Server se implementa en un único bosque y, a continuación, los usuarios están distribuidos en varios bosques. Atributos de los usuarios para mensajería unificada de Exchange deben replicarse sobre en el Skype para Business Server 2015 bosque.
    
    > [!NOTE]
    > Exchange se puede implementar en varios bosques. Cada organización de Exchange puede proporcionar mensajería unificada de Exchange a sus usuarios o mensajería unificada de Exchange se puede implementar en el mismo bosque que Skype para Business Server 2015. 
  
## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server-2015"></a>Instrucciones para la integración de Mensajería unificada local y Skype Empresarial Server 2015

Los siguientes procedimientos recomendados e instrucciones debe tenerse en cuenta cuando implemente Telefonía IP empresarial:
  
> [!IMPORTANT]
> Admite IPv6 sólo si también utiliza 4 UCMA de Exchange Unified Messaging (UM). 
  
- Implementar un Skype para servidor de 2015 Business Server Standard Edition o un grupo de servidores Front-End. Para obtener más información acerca de la instalación, vea [Implementar Skype para Business Server 2015](../../deploy/deploy.md) en la documentación de implementación.
    
- Colabore con los administradores de Exchange para confirmar las tareas que realizará cada uno y así garantizar una integración correcta y homogénea.
    
- Implementar las funciones de servidor de buzón de Exchange en cada bosque de Exchange Unified Messaging (UM) en el que desee habilitar a usuarios para la mensajería unificada de Exchange. Para obtener más información acerca de cómo instalar roles de servidor de Exchange, consulte la documentación de Microsoft Exchange Server de 2013.
    
    > [!IMPORTANT]
    > Cuando se instala Exchange Unified Messaging (UM), se configura para usar un certificado autofirmado. El certificado autofirmado no habilita Skype para que Business Server 2015 y mensajería unificada de Exchange confían entre sí, motivo por el cual es necesario solicitar un certificado independiente de una entidad emisora de certificados que confían en ambos servidores. 
  
- Si Skype para Business Server 2015 y mensajería unificada de Exchange se instala en diferentes bosques, configure cada bosque de Exchange para que confíe en el Skype para el bosque Business Server 2015 y el Skype para Business Server 2015 bosque para cada bosque de Exchange de confianza. También, establecer la configuración mensajería unificada de Exchange de los usuarios en los objetos de usuario en el Skype para Business Server 2015 bosque, normalmente mediante una secuencia de comandos o una herramienta entre bosques, como Identity Lifecycle Manager (ILM).
    
- Si es necesario, instale la Consola de administración de Exchange de modo que administre los servidores de mensajería unificada.
    
- Obtenga números de teléfono válidos para Outlook Voice Access y el operador automático.
    
- Si está utilizando una versión de mensajería unificada de Exchange anteriores a Service Pack 1 (SP1) de Microsoft Exchange Server 2010, nombres de coordenadas para Exchange UM SIP URI dial planes y planes de marcado de Telefonía IP empresarial. 
    
### <a name="deploying-redundant-exchange-um-servers"></a>Implementación de servidores redundantes de mensajería unificada de Exchange

> [!IMPORTANT]
> Recomendamos que implemente un mínimo de dos servidores en la mensajería unificada de Exchange se está ejecutando servicios para cada plan de marcado de Exchange UM SIP URI que configure para su organización. Además de ofrecer más capacidad, implementar servidores redundantes también proporciona una alta disponibilidad. En el caso de una falla del servidor, Skype para Business Server 2015 puede configurarse para que conmutar por error a otro servidor. 
  
Los siguientes ejemplos de configuraciones ofrecen resistencia a la mensajería unificada de Exchange.
  
**Ejemplo 1: Exchange UM resiliencia**

![Diagrama de resistencia de Mensajería unificada de Exchange](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)
  
En el Ejemplo 1, los servidores de mensajería unificada de Exchange 1 y 2 están habilitados en el centro de datos de Tukwila, y los servidores de mensajería unificada de Exchange 3 y 4 están habilitados en el centro de datos de Dublín. En el caso de que se produzca una interrupción de la mensajería unificada de Exchange en Tukwila, los registros de sistemas de nombre de dominio (DNS) A de los servidores 1 y 2 deben estar configurados para apuntar, respectivamente, a los servidores 3 y 4. En el caso de que se produzca una interrupción de la mensajería unificada de Exchange en Dublín, los registros DNS A de los servidores 3 y 4 deben estar configurados para apuntar, respectivamente, a los servidores 1 y 2.
  
> [!NOTE]
> Por ejemplo 1, se debe asignar uno de los siguientes certificados en cada servidor de mensajería unificada de Exchange: utilice un certificado con un carácter comodín en el nombre de alternativa de asunto (SAN) o poner el nombre de dominio completo (FQDN) de cada uno de los cuatro servidores mensajería unificada de Exchange en el SAN. 
  
**Ejemplo 2: Exchange UM resiliencia**

![Diagrama de resistencia de Mensajería unificada de Exchange](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)
  
En el Ejemplo 2, en condiciones normales de funcionamiento, los servidores de mensajería unificada de Exchange 1 y 2 están habilitados en el centro de datos de Tukwila, y los servidores de mensajería unificada de Exchange 3 y 4 están habilitados en el centro de datos de Dublín. Los cuatro servidores están incluidos en el plan de marcado URI del SIP de los usuarios de Tukwila; sin embargo, los servidores 3 y 4 están deshabilitados. En el caso de que se produzca una interrupción de la mensajería unificada de Exchange en Tukwila, por ejemplo, los servidores 1 y 2 de mensajería unificada de Exchange deben deshabilitarse y los servidores 3 y 4 de mensajería unificada de Exchange deben habilitarse para que el tráfico de mensajería unificada de Exchange de Tukwila se enrute a los servidores de Dublín.
  
Para obtener más información acerca de cómo habilitar o deshabilitar la mensajería unificada de Exchange 2013, vea [Integrar 2013 mensajería unificada de Exchange con Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=265372). La información proporcionada se aplica igualmente a Skype para Business Server 2015.
  
Para obtener más información acerca de cómo habilitar o deshabilitar mensajería unificada en Microsoft Exchange Server 2010, consulte:
  
- [Habilitar la mensajería unificada de Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204418)
    
- [Deshabilitar mensajería unificada en Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204416)
    
## <a name="see-also"></a>Vea también

#### 

[Descripción general del proceso de implementación para la integración local mensajería unificada y Skype para empresas](deployment-overview.md)

