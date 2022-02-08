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
description: 'Summary: Learn how to prepare your environment for an installation of Skype Empresarial Server. Descargue una prueba gratuita de Skype Empresarial Server desde el Centro de evaluación de Microsoft en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 8b129f164cb2650615cf20084f0617da419e4aeb
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386259"
---
# <a name="install-skype-for-business-server"></a>Instalar Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo preparar el entorno para una instalación de Skype Empresarial Server. Descargue una prueba gratuita de Skype Empresarial Server desde el Centro de evaluación de Microsoft en:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
En este artículo se muestra un ejemplo de instalación de Skype Empresarial Server. En este artículo no se tratan todos los procedimientos necesarios para realizar una instalación Skype Empresarial Server completa. El objetivo es proporcionar procedimientos de ejemplo en una topología definida estrechamente que incluya la funcionalidad básica de reunión y recurso compartido.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Información general sobre el proceso de instalación de Skype Empresarial Server

Una instalación de Skype Empresarial Server incluye muchos procedimientos diferentes. Los procedimientos que necesita para Skype Empresarial Server en ejecución en el entorno dependen de los detalles del entorno. Por ejemplo, si usa Windows server para DNS, se beneficiará del procedimiento de ejemplo para agregar una entrada DNS. Si usa otro sistema para DNS, debe seguir los procedimientos de su sistema DNS en particular. Esto es así para muchos de los procedimientos de esta sección.
  
Skype Empresarial Server está disponible en Standard Edition y Enterprise Edition. La diferencia principal es que Standard Edition no admite las características de alta disponibilidad que se incluyen con Enterprise Edition. 
  
Skype Empresarial Server es un producto avanzado y el proceso de instalación exacto depende en gran medida de sus circunstancias específicas. Esta sección le guiará por los pasos generales para instalar el producto. Sin embargo, cada procedimiento puede ser diferente según el entorno y las decisiones de planeación. Por ejemplo, para las organizaciones pequeñas un solo servidor, la ejecución de Skype Empresarial Server Standard Edition puede ser adecuada, mientras que una organización multinacional grande podría tener 50 servidores en ubicaciones de todo el mundo dedicadas al producto.
  
> [!NOTE]
> Para obtener información sobre las actualizaciones acumulativas más recientes, consulte [Actualizaciones para Skype Empresarial Server](https://support.microsoft.com/kb/3061064). Después de instalar la revisión CU1, un administrador debe ejecutar el  `Update-CsAdminRole` cmdlet. Este cmdlet es necesario para tener acceso a los nuevos cmdlets GCP a través de PowerShell remoto.
  
> [!IMPORTANT]
> Los procedimientos de esta sección sirven como ejemplo con un conjunto de requisitos definidos estrechamente y suponen que ya se han tomado decisiones específicas. Los procedimientos reales que necesita para instalar Skype Empresarial Server probablemente serán muy diferentes. Use los procedimientos de esta sección solo como ejemplo y no como una guía paso a paso para instalar Skype Empresarial Server en todos los entornos. 
  
La Skype Empresarial Server y la ejecución por primera vez implica ocho pasos principales. Debe comprender que los procedimientos de ejemplo de esta sección no son los únicos procedimientos necesarios para instalar Skype Empresarial Server. Los ocho pasos siguientes son simplemente ejemplos para ayudarle a comprender mejor el proceso general y a tener un entorno de trabajo básico en funcionamiento. Puede realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después de los pasos del 1 al 5, tal como se describe en el diagrama. Los ocho pasos son:
  
![Información general sobre el proceso de instalación.](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Instalar requisitos previos para Skype Empresarial Server](install-prerequisites.md): instalar requisitos previos en todos los servidores que forme la Skype Empresarial Server topología. Tenga en cuenta que los requisitos previos no son los mismos para todos los roles. Por ejemplo, los servidores que proporcionan el rol front-end tienen un conjunto de requisitos previos y los servidores que proporcionan un rol de director tienen un conjunto diferente de requisitos previos. Vea la documentación de planeación de requisitos previos para obtener más información.
    
- [Crear un recurso compartido de archivos en Skype Empresarial Server](create-a-file-share.md): Cree un recurso compartido de archivos que los servidores usarán en toda la Skype Empresarial Server topología.
    
- [Instalar herramientas administrativas en Skype Empresarial Server](install-administrative-tools.md): las herramientas administrativas incluyen el Generador de topologías y el Panel de control. Debe instalar las herramientas administrativas en al menos un servidor de la topología o en una estación de trabajo de administración de 64 bits que ejecute una versión del sistema operativo Windows compatible con Skype Empresarial Server.
    
- [Prepare Active Directory for Skype Empresarial Server](prepare-active-directory.md): Skype Empresarial Server funciona estrechamente con Active Directory. Debe preparar el dominio de Active Directory para que funcione con Skype Empresarial Server. Puede hacerlo a través del Asistente para implementación y solo se realiza una vez para el dominio. Esto se debe a que el proceso crea grupos y modifica el dominio, y solo debe hacerlo una vez.
    
- [Crear registros DNS para Skype Empresarial Server](create-dns-records.md): para que Skype Empresarial Server funcione correctamente, debe haber una serie de configuraciones DNS. Esto es para que los clientes sepan cómo acceder a los servicios y los servidores se conocen entre sí. Esta configuración solo debe completarse una vez por implementación, ya que una vez que se asigna una entrada DNS, está disponible en todo el dominio.
    
- [Crear y publicar](create-and-publish-new-topology.md) nueva topología en Skype Empresarial Server: para poder instalar el sistema Skype Empresarial Server en cada uno de los servidores de la topología, debe crear una topología y publicarla. Al publicar una topología, está cargando la información de topología en la base de datos del Almacén de administración central. Si se trata de un Enterprise Edition de servidores, estás creando la base de datos del Almacén de administración central la primera vez que publiques una topología nueva. Si esto es Standard Edition, debe ejecutar el proceso Preparar el primer servidor Standard Edition desde el Asistente para implementación antes de publicar una topología. Esto se prepara para Standard Edition instalando una instancia SQL Server Express Edition y creando el Almacén de administración central.
    
- [Instalar Skype Empresarial Server](install-skype-for-business-server.md) en servidores de la topología: una vez que la topología se carga en el Almacén de administración central y Active Directory sabe qué servidores realizarán los roles, debe instalar el sistema Skype Empresarial Server en cada uno de los servidores de la topología.
    
- [Compruebe](verify-the-topology.md) la topología en Skype Empresarial Server: después de publicar la topología y los componentes del sistema de Skype Empresarial Server instalados en cada uno de los servidores de la topología, está listo para comprobar que la topología funciona según lo esperado. Esto incluye comprobar que la configuración se haya propagado a todos los servidores de Active Directory para que todo el dominio sepa que Skype Empresarial está disponible en el dominio.
    

