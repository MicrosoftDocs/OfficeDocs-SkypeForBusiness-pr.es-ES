---
title: Crear base de datos
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: Topology Builder proporciona una forma de instalar bases de datos en un SQL Server web. Al instalar bases de datos mediante el Generador de topologías, la aplicación lee información de la topología y, a continuación, instala las bases de datos necesarias en el equipo SQL Server o en el clúster SQL Server especificado. Es el único tipo de instalación de bases de datos disponible mediante Topology Builder. Si necesita instalar una base de datos específica en un equipo específico, o si debe instalar una base de datos collocada Windows PowerShell, debe usar una interfaz de línea de comandos y el cmdlet Install-CsDatabase en su lugar.
ms.openlocfilehash: c854552d1a82e0f14492cff876189fd19f7eb7ba78d08269582f5a91c92ef028
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335190"
---
# <a name="create-database"></a>Crear base de datos
 
Topology Builder proporciona una forma de instalar bases de datos en un SQL Server web. Al instalar bases de datos mediante el Generador de topologías, la aplicación lee información de la topología y, a continuación, instala las bases de datos necesarias en el equipo SQL Server o en el clúster SQL Server especificado. Es el único tipo de instalación de bases de datos disponible mediante Topology Builder. Si necesita instalar una base de datos específica en un equipo específico o si debe instalar una base de datos collocada Windows PowerShell, debe usar una interfaz de línea de comandos y el cmdlet [Install-CsDatabase](/powershell/module/skype/install-csdatabase?view=skype-ps) en su lugar.
  
### <a name="creating-a-database"></a>Creación de una base de datos

1. Haga clic en el Skype Empresarial Server de 2015 y, a continuación, haga clic **en Instalar base de datos**.
    
2. En el **cuadro de** diálogo  Instalar bases de datos, en la página Crear base de datos, seleccione el nombre de dominio completo (FQDN) del almacén de SQL Server donde se van a crear las nuevas bases de datos.
    
3. Haga clic en **Avanzadas**. En el cuadro de diálogo de **selección de la ubicación del archivo de base de datos**, seleccione una de las opciones siguientes:
    
   - **Automatically determine database file location**. Si selecciona esta opción, Topology Builder usa un algoritmo integrado para elegir la ubicación de almacenamiento para los registros de las bases de datos y los archivos de datos.
    
   - **Use SQL Server instance defaults**. Si selecciona esta opción, no se usa el algoritmo integrado para elegir las ubicaciones de almacenamiento para los registros de las bases de datos y los archivos de datos. Por el contrario, los archivos de datos y registros se almacenan en las ubicaciones especificadas por las rutas de acceso predeterminadas de SQL Server (estas rutas debe configurarlas previamente un administrador de SQL Server). Los archivos de datos se almacenarán en la ubicación de archivos de datos de SQL Server predeterminada, mientras que los archivos de registro se almacenarán en la ubicación de archivos de registro de SQL Server predeterminada.
    
4. Haga clic en **Aceptar**.
    
5. En la página **Crear base de datos**, haga clic en **Siguiente**.
    
6. En la página que indica que **ha finalizado la creación de la base de datos**, haga clic en **Finalizar**.
