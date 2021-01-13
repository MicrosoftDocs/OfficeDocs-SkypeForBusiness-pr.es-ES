---
title: Instalar Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: 'Resumen: obtenga información sobre cómo preparar su entorno para una instalación de Skype Empresarial Server. Descargue una prueba gratuita de Skype Empresarial Server desde el Centro de evaluación de Microsoft en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: ef562a56e1129481954f9345a46483156bd1202f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801920"
---
# <a name="install-skype-for-business-server"></a>Instalar Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo preparar su entorno para una instalación de Skype Empresarial Server. Descargue una prueba gratuita de Skype Empresarial Server desde el Centro de evaluación de Microsoft en: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) .
  
Este artículo le guiará a través de un ejemplo de instalación de Skype Empresarial Server. En este artículo no se tratan todos los procedimientos necesarios para realizar una instalación completa de Skype Empresarial Server. El objetivo es proporcionar procedimientos de ejemplo en una topología estrechamente definida que incluya la funcionalidad básica de reunión y uso compartido.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Información general sobre el proceso de instalación de Skype Empresarial Server

Una instalación de Skype Empresarial Server incluye muchos procedimientos diferentes. Los procedimientos necesarios para que Skype Empresarial Server se ejecute en su entorno dependen de los detalles de su entorno. Por ejemplo, si usa Windows Server para DNS, se beneficiará del procedimiento de ejemplo para agregar una entrada DNS. Si usa otro sistema para DNS, debe seguir los procedimientos para su sistema DNS en particular. Esto es así para muchos de los procedimientos de esta sección.
  
Skype Empresarial Server está disponible en Standard Edition y Enterprise Edition. La principal diferencia es que Standard Edition no admite las características de alta disponibilidad que se incluyen con Enterprise Edition. 
  
Skype Empresarial Server es un producto avanzado y el proceso de instalación exacto depende en gran medida de sus circunstancias específicas. En esta sección se indican los pasos generales para instalar el producto. Sin embargo, cada procedimiento puede ser diferente según el entorno y las decisiones de planeación. Por ejemplo, para organizaciones pequeñas un único servidor, puede ser adecuado ejecutar Skype Empresarial Server Standard Edition, mientras que una organización multinacional grande podría tener 50 servidores en ubicaciones de todo el mundo dedicadas al producto.
  
> [!NOTE]
> Para obtener información sobre las actualizaciones acumulativas más recientes, consulte [Actualizaciones de Skype Empresarial Server.](https://support.microsoft.com/kb/3061064) Después de instalar la revisión CU1, un administrador debe ejecutar el  `Update-CsAdminRole` cmdlet. Este cmdlet es necesario para tener acceso a los nuevos cmdlets GCP a través de PowerShell remoto.
  
> [!IMPORTANT]
> Los procedimientos de esta sección sirven como ejemplo con un conjunto de requisitos definido estrechamente y suponen que ya se han tomado decisiones específicas. Los procedimientos reales que necesita para instalar Skype Empresarial Server probablemente serán muy diferentes. Use los procedimientos de esta sección solo como ejemplo y no como guía paso a paso para instalar Skype Empresarial Server en cada entorno. 
  
Poner Skype Empresarial Server en funcionamiento por primera vez implica ocho pasos principales. Debe comprender que los procedimientos de ejemplo de esta sección no son los únicos procedimientos necesarios para instalar Skype Empresarial Server. Los ocho pasos siguientes son simplemente ejemplos que le ayudarán a comprender mejor el proceso general y a obtener un entorno de trabajo básico en funcionamiento. Puede realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después de los pasos 1 a 5, tal como se indica en el diagrama. Los ocho pasos son:
  
![Información general sobre el proceso de instalación.](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Instalar requisitos previos para Skype Empresarial Server:](install-prerequisites.md) instale los requisitos previos en todos los servidores que forme la topología de Skype Empresarial Server. Tenga en cuenta que los requisitos previos no son los mismos para todos los roles. Por ejemplo, los servidores que proporcionan el rol front-end tienen un conjunto de requisitos previos y los servidores que proporcionan un rol de director tienen un conjunto diferente de requisitos previos. Vea la documentación de planeación de requisitos previos para obtener más información.
    
- [Crear un recurso compartido de archivos en Skype](create-a-file-share.md) Empresarial Server: cree un recurso compartido de archivos que los servidores usarán en toda la topología de Skype Empresarial Server.
    
- [Instalar herramientas administrativas en Skype Empresarial Server:](install-administrative-tools.md) las herramientas administrativas incluyen el Generador de topologías y el Panel de control. Debe instalar las herramientas administrativas en al menos un servidor de la topología o en una estación de trabajo de administración de 64 bits que ejecute una versión del sistema operativo Windows compatible con Skype Empresarial Server.
    
- [Preparar Active Directory para Skype Empresarial Server:](prepare-active-directory.md) Skype Empresarial Server funciona estrechamente con Active Directory. Debe preparar el dominio de Active Directory para que funcione con Skype Empresarial Server. Puede hacerlo a través del Asistente para la implementación y solo se realiza una vez para el dominio. Esto se debe a que el proceso crea grupos y modifica el dominio, y solo necesita hacerlo una vez.
    
- [Crear registros DNS para Skype Empresarial Server:](create-dns-records.md) para que Skype Empresarial Server funcione correctamente, debe haber una serie de configuraciones DNS. Esto es para que los clientes sepan cómo acceder a los servicios y los servidores se conocen entre sí. Esta configuración solo debe completarse una vez por implementación porque, una vez que asigne una entrada DNS, estará disponible en todo el dominio.
    
- [Crear y publicar](create-and-publish-new-topology.md) una topología nueva en Skype Empresarial Server: antes de instalar el sistema de Skype Empresarial Server en cada uno de los servidores de la topología, debe crear una topología y publicarla. Cuando publique una topología, cargará la información de la topología en la base de datos del Almacén de administración central. Si se trata de un grupo de servidores Enterprise Edition, va a crear la base de datos del Almacén de administración central la primera vez que publique una topología nueva. Si se trata de Standard Edition, debe ejecutar el proceso Preparar el primer servidor Standard Edition desde el Asistente para la implementación antes de publicar una topología. Esto se prepara para Standard Edition instalando una instancia de SQL Server Express Edition y creando el Almacén de administración central.
    
- [Instalar Skype](install-skype-for-business-server.md) Empresarial Server en los servidores de la topología: una vez que la topología se carga en el Almacén de administración central y Active Directory sabe qué servidores realizarán los roles, debe instalar el sistema de Skype Empresarial Server en cada uno de los servidores de la topología.
    
- Compruebe la topología en Skype Empresarial [Server:](verify-the-topology.md) una vez publicada la topología y los componentes del sistema de Skype Empresarial Server instalados en cada uno de los servidores de la topología, estará listo para comprobar que la topología funciona según lo esperado. Esto incluye comprobar que la configuración se ha propagado a todos los servidores de Active Directory para que todo el dominio sepa que Skype Empresarial está disponible en el dominio.
    

