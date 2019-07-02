---
title: Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 'Resumen: Lea este tema para obtener información sobre los requisitos de hardware y software para el servidor de chat persistente en Skype empresarial Server 2015.'
ms.openlocfilehash: e700b76c8af29a0c877c1dc594244a299b8a3904
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418448"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información sobre los requisitos de hardware y software para el servidor de chat persistente en Skype empresarial Server 2015.
  
El servidor de chat persistente puede instalarse con Skype empresarial Server 2015 Enterprise Edition o Standard Edition. Los requisitos dependen de la edición de Skype empresarial Server 2015 que haya instalado y de los requisitos de rendimiento de su empresa. Enterprise Edition puede admitir hasta 80 000 usuarios simultáneos; Standard Edition puede admitir hasta 20 000 usuarios simultáneos. El chat persistente consiste de un componente front-end y de un componente de base de datos de SQL back-end.
  
Antes de implementar un servidor de chat persistente, debe asegurarse de que se cumplan los siguientes requisitos de hardware y software:
  
- Hardware que cumple con los requisitos mínimos para admitir Skype empresarial Server 2015, servidor de chat persistente, servidores de base de datos y servidores de archivos. Para obtener más información, consulte [requisitos del servidor de Skype empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Sistemas operativos y software de base de datos compatibles
    
    Para obtener más información sobre los sistemas operativos y el software de base de datos compatibles, y los requisitos de Windows Update, consulte [requisitos del servidor de Skype empresarial server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Servidor front-end 2015 de Skype empresarial Server. El servidor front-end es la base del enrutamiento SIP (Protocolo de inicio de sesión), que hace posible la comunicación entre equipos que ejecutan el servidor de chat persistente y la funcionalidad de chat persistente. 
    
- Software Message Queue. Utilizado por el servidor de chat persistente y por el servicio de cumplimiento de chat persistente, si se ha implementado.
    
En las siguientes secciones se describen los requisitos específicos para el servidor de chat persistente y la base de datos que almacena los datos persistentes del chat.

> [!NOTE] 
> Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams](/microsoftteams/upgrade-start-here). Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015. 
  
## <a name="front-end-server-requirements"></a>Requisitos del servidor front-end

Los requisitos del servidor front-end dependen de si va a implementar un servidor de chat persistente con Skype empresarial Server 2015 Enterprise Edition o Standard Edition.
  
- Si va a implementar un servidor de chat persistente con Skype empresarial Server 2015 Enterprise Edition, puede implementar el servidor front-end del servidor de chat persistente en uno o más equipos independientes del grupo Enterprise Edition. No puede Collocate los servidores front-end de chat persistentes en el servidor front-end de Skype empresarial Server 2015. 
    
    Un solo servidor de cliente de servidor de chat persistente puede admitir usuarios activos de 20.000. Puede tener un grupo de servidores de chat persistente con hasta 4 servidores frontales activos, por lo que se admite un total de 80.000 usuarios simultáneos. 
    
- Si va a implementar un servidor de chat persistente con Skype empresarial Server 2015 Standard Edition, puede Collocate chat persistente con el servidor front-end. Esta implementación de servidor único puede admitir hasta 20 000 usuarios. 
    
## <a name="persistent-chat-server-database-requirements"></a>Requisitos de base de datos del servidor de chat persistente

El servidor de chat persistente requiere un software de base de datos de SQL Server para almacenar el historial y el contenido de los salones de chat, los datos de configuración, los datos de aprovisionamiento de usuarios y otros metadatos relevantes. De manera opcional, usa la base de datos de cumplimiento de chat persistente para almacenar los datos de cumplimiento. Las bases de datos de chat persistente se pueden combinar en el mismo SQL Server o, incluso, en la misma instancia de SQL, como las bases de datos back-end. 
  
- Si va a instalar un servidor de chat persistente con Skype empresarial Server 2015 Enterprise Edition, para garantizar un rendimiento óptimo, le recomendamos que instale el almacén de archivos de chat persistente.
    
- Si va a instalar un servidor de chat persistente con Skype empresarial Server 2015 Standard Edition, puede implementar el servidor de back-end de almacenamiento de chats persistentes en la instancia local de SQL Server Express.
    
- La base de datos de chat persistente (MGC) y la base de datos de cumplimiento (mgccomp) se pueden encontrar en la misma instancia de SQL Server o en diferentes servidores SQL.
    
Para preparar una plataforma de servidor de base de datos, asegúrese de que cada equipo cumpla los requisitos de hardware y, luego, instale el software que se necesita como requisito previo. La plataforma de servidor de los servidores de base de datos de chat persistente requiere el mismo hardware que el servidor de base de datos back-end de Skype empresarial Server 2015. Para más información, vea [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
  
Confirma que una de las siguientes aplicaciones de software está instalada en el servidor de bases de datos:

- Microsoft SQL Server 2017 con el Service Pack más reciente.

- Microsoft SQL Server 2016 con Service Pack 1 y debe ejecutarse con la actualización acumulativa 7 o versiones posteriores de Skype empresarial Server. Recomendamos ejecutar SQL Server 2016 con el Service Pack más reciente. Para obtener más información sobre cómo instalar Microsoft SQL Server 2016, consulte [instalar SQL server 2016](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).

- Microsoft SQL Server 2014 y debe ejecutarse con la actualización acumulativa 6 o versiones posteriores de Skype empresarial Server. Recomendamos ejecutar SQL Server 2014 con el Service Pack más reciente. Para obtener más información sobre cómo instalar Microsoft SQL Server 2014, consulte [instalar SQL server 2014](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).

- Microsoft SQL Server 2012 (edición de 64) y recomendamos la ejecución con el Service Pack más reciente. Para obtener más información sobre cómo instalar Microsoft SQL Server 2012, consulte [instalar SQL server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).

## <a name="persistent-chat-server-certificate-requirements"></a>Requisitos de certificados del servidor de chat persistente

Para obtener detalles sobre la adquisición de certificados, la creación de la base de datos de SQL Server y la creación de almacenes de archivos, consulte [implementar Skype empresarial server 2015](../../deploy/deploy.md). 
  
## <a name="for-more-information"></a>Para obtener más información

Para obtener más información sobre los requisitos de hardware y software, mira los siguientes temas:
  
- [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

