# Besoin cnmh

## Empathie avec service social

Une séance d’empathie a été réalisée avec Khawla souan, en tant que personnel du service social, le 20 mars 2023.

![service social Carte d'empathie](./images/service-social.png)


## Code source 

Code source d'entretien social

```bash
public function FormEntretienSocial($PatientID){
        $editMode = false; 
        $couvertureMedical = new CouvertureMedicalRepository;
        $couverture_medical = $couvertureMedical->all();
        $typeHandicap = new TypeHandicapRepository;
        $type_handicap = $typeHandicap->all();
        $service = new ServiceRepository;
        $services = $service->all();
        $latestDossier = $this->dossierPatientRepository->NumeroDossier();
        $counter = $latestDossier ? (int)substr($latestDossier, 2) + 1 : 1;
        $numeroDossier = 'A-' . $counter;
        $PatientID = $PatientID;
        return view('PoleSocial.dossier_patients.entretien', compact('type_handicap', 'couverture_medical','services','editMode','PatientID','numeroDossier'));
}

```
