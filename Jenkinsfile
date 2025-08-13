stage('Install Dependencies') {
    steps {
        sh 
            # Create a virtual environment in the workspace
            python3 -m venv venv
            
            # Activate the virtual environment
            . venv/bin/activate
            
            # Upgrade pip inside the venv
            pip install --upgrade pip
            
            # Install dependencies from requirements.txt inside venv
            pip install -r requirements.txt
        
    }
}
