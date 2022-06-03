---
title: Instalar Skype Empresarial Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: 'Resumen: obtenga información sobre cómo preparar el entorno para una instalación de Skype Empresarial Server.'
ms.openlocfilehash: 32003fc1c269a0bf1b59afc965099851b6406ed6
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860591"
---
# <a name="install-skype-for-business-server"></a>Instalar Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo preparar el entorno para una instalación de Skype Empresarial Server.
  
Este artículo le guiará a través de una instalación de ejemplo de Skype Empresarial Server. Este artículo no intenta cubrir todos los procedimientos que necesita para realizar una instalación completa Skype Empresarial Server. El objetivo es proporcionar procedimientos de ejemplo en una topología estrechamente definida que incluya la funcionalidad básica de reunión y uso compartido.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Introducción al proceso de instalación de Skype Empresarial Server

Una instalación de Skype Empresarial Server incluye muchos procedimientos diferentes. Los procedimientos necesarios para que Skype Empresarial Server se ejecuten en el entorno dependen de los detalles del entorno. Por ejemplo, si usa Windows Server para DNS, se beneficiará del procedimiento de ejemplo para agregar una entrada DNS. Si usa otro sistema para DNS, debe seguir los procedimientos para el sistema DNS determinado. Esto es así para muchos de los procedimientos de esta sección.
  
Skype Empresarial Server está disponible en Standard Edition y Enterprise Edition. La principal diferencia es que Standard Edition no admite las características de alta disponibilidad que se incluyen con Enterprise Edition. 
  
Skype Empresarial Server es un producto avanzado y el proceso de instalación exacto depende en gran medida de sus circunstancias específicas. Esta sección le guiará por los pasos generales para instalar el producto. Sin embargo, cada procedimiento puede ser diferente en función del entorno y las decisiones de planeamiento. Por ejemplo, para organizaciones pequeñas un único servidor, ejecutar Skype Empresarial Server Standard Edition podría ser adecuado, mientras que una gran organización multinacional podría tener 50 servidores en ubicaciones de todo el mundo dedicadas al producto.
  
> [!NOTE]
> Para obtener información sobre las actualizaciones acumulativas más recientes, consulte [Actualizaciones para Skype Empresarial Server](https://support.microsoft.com/kb/3061064). Después de instalar la revisión cu1, un administrador debe ejecutar el  `Update-CsAdminRole` cmdlet. Este cmdlet es necesario para acceder a los nuevos cmdlets de GCP a través de PowerShell remoto.
  
> [!IMPORTANT]
> Los procedimientos de esta sección sirven como ejemplo mediante un conjunto de requisitos definidos estrechamente y asumen que ya se han tomado decisiones específicas. Es probable que los procedimientos reales que necesita para instalar Skype Empresarial Server sean muy diferentes. Use los procedimientos de esta sección solo como ejemplo y no como guía paso a paso para instalar Skype Empresarial Server en todos los entornos. 
  
Poner Skype Empresarial Server en funcionamiento por primera vez implica ocho pasos principales. Debe comprender que los procedimientos de ejemplo de esta sección no son los únicos procedimientos necesarios para instalar Skype Empresarial Server. Los ocho pasos siguientes son simplemente ejemplos que le ayudarán a comprender mejor el proceso general y a poner en funcionamiento un entorno de trabajo básico. Puede realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden, y después de los pasos del 1 al 5, como se describe en el diagrama. Los ocho pasos son:
  
![Introducción al proceso de instalación.](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Instalar requisitos previos para Skype Empresarial Server](install-prerequisites.md): instale los requisitos previos en todos los servidores que componen la topología de Skype Empresarial Server. Tenga en cuenta que los requisitos previos no son los mismos para todos los roles. Por ejemplo, los servidores que proporcionan el rol de front-end tienen un conjunto de requisitos previos y los servidores que proporcionan un rol de director tienen un conjunto diferente de requisitos previos. Consulte la documentación de planeamiento de requisitos previos para obtener más detalles.
    
- [Crear un recurso compartido de archivos en Skype Empresarial Server](create-a-file-share.md): cree un recurso compartido de archivos que los servidores usarán en toda la topología de Skype Empresarial Server.
    
- [Instalar herramientas administrativas en Skype Empresarial Server](install-administrative-tools.md) : las herramientas administrativas incluyen el Generador de topologías y Panel de control. Debe instalar las herramientas administrativas en al menos un servidor de la topología o una estación de trabajo de administración de 64 bits que ejecute una versión Windows del sistema operativo que sea compatible con Skype Empresarial Server.
    
- [Preparar Active Directory para Skype Empresarial Server](prepare-active-directory.md): Skype Empresarial Server funciona estrechamente con Active Directory. Debe preparar el dominio de Active Directory para trabajar con Skype Empresarial Server. Puede hacerlo a través del Asistente para la implementación y solo se hace una vez para el dominio. Esto se debe a que el proceso crea grupos y modifica el dominio, y debe hacerlo solo una vez.
    
- [Crear registros DNS para Skype Empresarial Server](create-dns-records.md) : para que Skype Empresarial Server funcione correctamente, debe haber una serie de configuraciones dns. Esto es para que los clientes sepan cómo acceder a los servicios y los servidores se conozcan entre sí. Esta configuración solo debe completarse una vez por implementación porque, una vez que se asigna una entrada DNS, está disponible en todo el dominio.
    
- [Crear y publicar una nueva topología en Skype Empresarial Server](create-and-publish-new-topology.md) : para poder instalar el sistema de Skype Empresarial Server en cada uno de los servidores de la topología, debe crear una topología y publicarla. Al publicar una topología, carga la información de la topología en la base de datos del Almacén de administración central. Si se trata de un grupo de Enterprise Edition, va a crear la base de datos del Almacén de administración central la primera vez que publique una nueva topología. Si esto es Standard Edition, debe ejecutar el proceso Prepare First Standard Edition Server desde el Asistente para la implementación antes de publicar una topología. Esto se prepara para Standard Edition instalando una instancia de SQL Server Express Edition y creando el Almacén de administración central.
    
- [Instalar Skype Empresarial Server en servidores de la topología](install-skype-for-business-server.md): una vez que la topología se carga en el Almacén de administración central y Active Directory sabe qué servidores realizarán qué roles, debe instalar el sistema de Skype Empresarial Server en cada uno de los servidores de la topología.
    
- [Compruebe la topología en Skype Empresarial Server](verify-the-topology.md): una vez publicada la topología y los componentes del sistema Skype Empresarial Server instalados en cada uno de los servidores de la topología, estará listo para comprobar que la topología funciona según lo esperado. Esto incluye comprobar que la configuración se ha propagado a todos los servidores de Active Directory para que todo el dominio sepa que Skype Empresarial está disponible en el dominio.
    

