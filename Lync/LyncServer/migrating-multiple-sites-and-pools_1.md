---
title: Migración de varios sitios y grupos de servidores
TOCTitle: Migración de varios sitios y grupos de servidores
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49889047
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migración de varios sitios y grupos de servidores

 

_**Última modificación del tema:** 2012-08-26_

Lync Server 2013 admite implementaciones multisitio y de varios grupos. En el proceso de migrar múltiples grupos de Office Communications Server 2007 R2 a Lync Server 2013, se deben tener en cuenta las siguientes consideraciones:

1.  Tras implementar un grupo de servidores piloto Lync Server 2013, necesita definir un subconjunto de usuarios piloto que se trasladarán al grupo de servidores Lync Server 2013 y una metodología y una metodología para validar la funcionalidad de los usuarios.

2.  Después de implementar un servidor perimetral en el grupo piloto, debe comprobar que los usuarios externos pueden comunicarse con el grupo de Lync Server 2013.

3.  Después de trasladar las rutas federadas de los servidores perimetrales de Office Communications Server 2007 R2 a los servidores perimetrales de Lync Server 2013 pilotos, debe comprobar que los usuarios federados pueden comunicarse con el grupo de Lync Server 2013.

4.  Tras mover todos los usuarios y objetos de contacto que no sean usuarios, deberá validar que el grupo de Office Communications Server 2007 R2 está vacío.

5.  Tras comprobar que el grupo de Office Communications Server 2007 R2 está vacío, podrá desactivar el grupo.
    
    Para obtener información detallada sobre cómo desactivar los servidores y el grupo de servidores heredados Office Communications Server 2007 R2, vea [Fase 10: Retirar sitios heredados](phase-10-decommission-legacy-site.md).

