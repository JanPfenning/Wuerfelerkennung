# Performanzvergleich des YOLO-Algorithmus mit einem neuen zweistufigen CNN Bilderkenner

Dieses Repository beinhaltet alle praktischen Bestandteile der Studienarbeit von Konrad Schewe und Jan Pfenning zum Thema Bildverarbeitung.
In der Arbeit geht es darum, die Würfel zu erkennen und deren angezeigten Augenzahlen abzulesen. 
Die Pipeline soll zur erkennung der Würfel während eines "Kniffel" Spiels hinzugezogen werden können.
Ein Bild, welches als Eingabe dient, zeigt also genau 5 Würfel.
Es wird ein Bilderkennungsansatz mit dem "YOLO"-Algorithmus mit eigens implementierten und trainierten CNN verglichen.
Dieses CNN erhält segmentierte Bildbereiche welche je nur einen Würfel zeigen.
Diese Segmentierung wurde über Binärisierung und Flood-Filling sowie über Kantendetektion umgesetzt.

## Repository

Der Ordner Code beinhaltet die Implementierung der Problemlösung als Jupyter.
Der Order Artifacts enthält Dateien, die für die Ausführung des Codes essentiell sind.
Die Artifacts müssen in Colab hochgeladen werden und sind nach jeder Sitzung verschwunden.

## Implementierung / Ausführung

Der gesamte Code dieses Repositories wurde als JupyterNotebook auf Google Colab ausgeführt.
Wie der Code zu verwenden und interpretieren ist, ist in der Studienarbeit und im Folgenden beschrieben.

### YOLO

Zu der YOLO-Implementierung gehören die drei Notebooks:
- Code/yolo/yolo_train.ipynb: Training des YOLO-CNN
- Code/yolo/yolo_predict.ipynb: Testen des trainierten CNN auf eigenen (Test-)Bildern
- Code/yolo/yolo_test.ipynb: Gibt Metriken zu dem Test-Datensatz zurück

Die für die Ausführung benötigten Dateien liegen unter Artifacts/yolo.

### CNN (Klassifikations Notebook)
Der erste Teil im CNN Notebook sind präprozessierungen, die nur einmal ausgeführt wurden, um in Zukunft die experimente schneller laufen lassen zu können.
Im Bereich "Read DF" kann das Dataframe aus den Artifacts eingelesen werden, welches verwendet werden soll.

Im folgenden Bereich wird ein Keras Modell spezifiziert.
Danach werden Trainings und Testdaten (zu finden in den Artifacts) geladen und das Model trainiert.
Die Nächste Sektion zeigt die Ergebnisse Grafisch an.

### Objektsegmentierung

In diesem Notebook sind verschiedene Methoden zur Segmentierung getestet worden. Die Verwendungen finden sich in der End-to-End Pipeline wieder.

### End-to-End Pipeline

Zu beginn werden die Pandas-Dataframes aus der Google Drive geladen. Das kann durch einfaches hochladen ersetzt werden.
Im Kapitel "End to End Pipeline Image to Boxes and Classes" wird die Pipeline samt funktionen definiert.
Das Kapitel darüber dient dem Testen der einzelnen Stufen und zum debugging.