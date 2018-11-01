---
title: Migrar múltiples sitios y grupos de servidores
TOCTitle: Migrar múltiples sitios y grupos de servidores
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48276278
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrar múltiples sitios y grupos de servidores

 

_**Última modificación del tema:** 2012-09-17_

Lync Server 2013 admite implementaciones multisitio y de varios grupos. En el proceso de migrar múltiples grupos de Lync Server 2010 a Lync Server 2013, se deben tener en cuenta las siguientes consideraciones:

1.  Después de implementar un grupo piloto de Lync Server 2013, debe definir un subconjunto de usuarios piloto que se moverán al grupo de Lync Server 2013 y una metodología para validar la funcionalidad de los usuarios. Por ejemplo, después de mover un usuario al grupo piloto, compruebe que la directiva de conferencia del usuario se ha movido a Lync Server 2013.

2.  Después de implementar un servidor perimetral en el grupo piloto, debe comprobar que los usuarios externos pueden comunicarse con el grupo de Lync Server 2013.

3.  Después de trasladar las rutas federadas de los servidores perimetrales de Lync Server 2010 a los servidores perimetrales de Lync Server 2013 pilotos, debe comprobar que los usuarios federados pueden comunicarse con el grupo de Lync Server 2013.

4.  Tras mover todos los usuarios y objetos de contacto que no sean usuarios, deberá validar que el grupo de Lync Server 2010 está vacío.

5.  Tras comprobar que el grupo de Lync Server 2010 está vacío, podrá desactivar el grupo.
    
    Para obtener información detallada sobre cómo desactivar los servidores y el grupo de servidores heredados Lync Server 2010, vea [Fase 8: Retirar grupos heredados](phase-8-decommission-legacy-pools.md).

