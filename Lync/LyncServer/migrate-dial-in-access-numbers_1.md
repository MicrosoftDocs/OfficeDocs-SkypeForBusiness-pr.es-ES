---
title: Migrar números de acceso telefónico
TOCTitle: Migrar números de acceso telefónico
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48275291
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrar números de acceso telefónico

 

_**Última modificación del tema:** 2012-09-26_

Para migrar números de acceso telefónico es necesario realizar dos pasos: ejecutar el cmdlet **Import-CsLegacyConfiguration** (completado previamente en [Importar directivas y configuraciones](import-policies-and-settings.md)) para migrar planes de marcado y otras configuraciones de número de acceso telefónico y ejecutar el cmdlet **Move-CsApplicationEndpoint** para migrar los objetos de contacto.

## Para migrar los números de acceso telefónico

1.  Abra la herramienta administrativa de Office Communications Server 2007 R2.

2.  En el árbol de consola, haga clic con el botón derecho en el nodo del bosque, haga clic en **Propiedades** y, a continuación, haga clic en **Propiedades de operador de conferencia**.

3.  En la pestaña **Números de teléfono de acceso** haga clic en **Servido por grupo de seguidores** para ordenar los números de teléfono de acceso por su grupo asociado e identificar todos los números de acceso para el grupo del que está migrando.

4.  Para identificar el URI del SIP para cada número de acceso, haga doble clic en el número de acceso para abrir el cuadro de diálogo **Editar número de operador de conferencia** y busque en **URI del SIP** .

5.  Abra Shell de administración de Lync Server.

6.  Para mover cada número de acceso telefónico a un grupo de servidores hospedado en Lync Server 2013, ejecute:
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  En el grupo administrativo Office Communications Server 2007 R2, en la pestaña **Números de teléfono de acceso** , verifique que no queda ningún número de acceso telefónico para el grupo de servidores Office Communications Server 2007 R2 desde el que está haciendo la migración.

