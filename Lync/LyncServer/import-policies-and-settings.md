---
title: Importar directivas y configuraciones
TOCTitle: Importar directivas y configuraciones
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48276393
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Importar directivas y configuraciones

 

_**Última modificación del tema:** 2012-09-28_

Tras combinar la información de la topología de Office Communications Server 2007 R2 con el grupo piloto de Lync Server 2013, debe ejecutar un cmdlet del Shell de administración de Lync Server 2013 para migrar las directivas y la configuración de Office Communications Server 2007 R2 al grupo piloto de Lync Server 2013.

El cmdlet **Import-CsLegacyConfiguration** importa directivas, rutas de voz, planes de marcado, direcciones URL de Communicator Web Access y números de acceso telefónico a Lync Server 2013.

## Para migrar directivas y configuración

1.  En el servidor front-end de Lync Server 2013, inicie el Shell de administración de Lync Server.

2.  En la línea de comandos, escriba:
    
        Import-CsLegacyConfiguration
    
    Tras importar las directivas, use el siguiente procedimiento para ver las directivas importadas en el Panel de control de Lync Server.

## Par ver directivas importadas

1.  Abra el Panel de control de Lync Server 2013.

2.  Haga clic en **Enrutamiento de voz** y vea las directivas importadas.

3.  Haga clic en **Conferencia** y vea las directivas importadas.

4.  Haga clic en **Federación y acceso externo** y vea las directivas importadas.

5.  Haga clic en **Supervisión y archivado** y vea las directivas importadas.

