---
title: Procedimientos recomendados de copia de seguridad y restauración
TOCTitle: Procedimientos recomendados de copia de seguridad y restauración
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh202184(v=OCS.15)
ms:contentKeyID: 52061751
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Procedimientos recomendados de copia de seguridad y restauración

 

_**Última modificación del tema:** 2013-02-21_

Esta sección incluye dos tipos de procedimientos recomendados:

  - Procedimientos recomendados de copia de seguridad y restauración.

  - Procedimientos recomendados para minimizar el impacto de un desastre.

## Procedimientos recomendados de copia de seguridad y restauración

Aplique los siguientes procedimientos recomendados para facilitar los procesos de copia de seguridad y restauración:

  - Haga copias de seguridad periódicamente y a intervalos apropiados. La rutina más sencilla y habitual a la hora de programar copias de seguridad es hacer cada noche copias completas de toda la base de datos de SQL Server. Así, si hay que restaurar el sistema, solo se necesita una copia de seguridad y no suele perderse más de un día de datos.

  - Si usa cmdlets o el Panel de control de Lync Server para hacer cambios de configuración, use el cmdlet **Export-CsConfiguration** para hacer una copia de seguridad tipo instantánea del archivo de configuración de topología (Xds.mdf) tras hacer los cambios. Así, si necesita restaurar sus bases de datos, no perderá los cambios. Observe que esta configuración se guarda en una copia de seguridad en formato XML y en un archivo comprimido ZIP.

  - Asegúrese de que la carpeta compartida que prevé usar para hacer copias de seguridad de Lync Server tiene suficiente espacio en el disco para guardar todos los datos de los que haga copia de seguridad.

  - Programe las copias de seguridad para que se hagan en los momentos en los que se suela usar menos Lync Server. De esta manera, mejorará el rendimiento del servidor y la experiencia del usuario.

  - Asegúrese de que la ubicación en la que guarda la copia de seguridad de los datos sea segura (recomendamos una ubicación remota).

  - Guarde las copias de seguridad en una ubicación de de fácil acceso por si necesita restaurar los datos.

  - Planee y programe pruebas periódicas de los procesos de restauración con el apoyo de su organización.

  - Valide los procesos de copia de seguridad y restauración por adelantado para asegurarse de que funcionan según lo esperado.

## Procedimientos recomendados para minimizar el impacto de un desastre

La mejor estrategia para enfrentarse a interrupciones del servicio de consecuencias desastrosas (provocadas por situaciones incontrolables como cortes del suministro eléctrico o errores repentinos de hardware) es dar por sentado que ocurrirán y hacer los planes pertinentes.

Si los servicios de Lync, con un mínimo de interrupción, son fundamentales para su organización, considere la opción de implementar grupos emparejados de servidores front-end, tal como se describe en [Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Después de hacerlo, si se produce un desastre en uno de estos grupos, un administrador podrá mover los usuarios de ese grupo para que reciban el servicio del otro grupo con un tiempo de inactividad mínimo.

En los planes de administración de desastres que implemente como parte de su estrategia de copia de seguridad y restauración, se debe tener en cuenta lo siguiente:

  - Tenga siempre a mano los medios de software y las actualizaciones de software y firmware.

  - Mantenga registros de hardware y software.

  - Haga copias de seguridad de sus datos periódicamente y supervise la integridad de las mismas.

  - Forme a su personal en recuperación de desastres, documente todos los procedimientos y lleve a cabo simulacros de recuperación de desastres.

  - Tenga siempre a mano hardware de repuesto. Si tiene un contrato de nivel de servicio (SLA), póngase en contacto con los distribuidores y minoristas de hardware para obtener rápidamente equipos de repuesto.

  - Separe la ubicación de sus archivos de registro de transacciones (archivos .ldf) y los archivos de bases de datos (archivos .mdf).

