<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ezee Fiber Technical Support Note Generator</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
            background-color: #f9fafb;
            padding: 2rem 1rem;
            line-height: 1.6;
        }

        .container {
            max-width: 1000px;
            margin: 0 auto;
            background: white;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            padding: 2rem;
        }

        h1 {
            font-size: 2rem;
            color: #111827;
            text-align: center;
            margin-bottom: 0.5rem;
        }

        h2 {
            font-size: 1.25rem;
            color: #4b5563;
            text-align: center;
            padding-bottom: 1.5rem;
            border-bottom: 2px solid #e5e7eb;
            margin-bottom: 2rem;
        }

        .form-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1.5rem;
        }

        .form-group {
            margin-bottom: 1rem;
        }

        .form-group.full-width {
            grid-column: 1 / -1;
        }

        label {
            display: block;
            font-weight: 600;
            color: #374151;
            margin-bottom: 0.5rem;
            font-size: 0.875rem;
        }

        input[type="text"],
        textarea {
            width: 100%;
            padding: 0.75rem;
            border: 1px solid #d1d5db;
            border-radius: 0.375rem;
            font-size: 1rem;
            transition: border-color 0.2s, box-shadow 0.2s;
        }

        input[type="text"]:focus,
        textarea:focus {
            outline: none;
            border-color: #3b82f6;
            box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.1);
        }

        textarea {
            resize: vertical;
            min-height: 80px;
        }

        .yes-no-buttons {
            display: flex;
            gap: 0.5rem;
        }

        .yes-no-buttons button {
            flex: 1;
            padding: 0.75rem 1.5rem;
            border: none;
            border-radius: 0.375rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.2s;
            background-color: #e5e7eb;
            color: #374151;
        }

        .yes-no-buttons button:hover {
            background-color: #d1d5db;
        }

        .yes-no-buttons button.active-yes {
            background-color: #16a34a;
            color: white;
        }

        .yes-no-buttons button.active-no {
            background-color: #dc2626;
            color: white;
        }

        .action-buttons {
            margin-top: 2rem;
            padding-top: 2rem;
            border-top: 2px solid #e5e7eb;
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn {
            padding: 0.75rem 2rem;
            border: none;
            border-radius: 0.5rem;
            font-weight: 600;
            cursor: pointer;
            font-size: 1rem;
            transition: all 0.2s;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }

        .btn-primary {
            background-color: #2563eb;
            color: white;
        }

        .btn-primary:hover {
            background-color: #1d4ed8;
        }

        .btn-secondary {
            background-color: #6b7280;
            color: white;
        }

        .btn-secondary:hover {
            background-color: #4b5563;
        }

        .btn-success {
            background-color: #16a34a;
            color: white;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .btn-success:hover {
            background-color: #15803d;
        }

        .output-section {
            margin-top: 2rem;
            padding-top: 2rem;
            border-top: 2px solid #e5e7eb;
            display: none;
        }

        .output-section.show {
            display: block;
        }

        .output-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1rem;
            flex-wrap: wrap;
            gap: 1rem;
        }

        .output-header h3 {
            font-size: 1.25rem;
            color: #111827;
        }

        .output-box {
            background-color: #f3f4f6;
            padding: 1.5rem;
            border-radius: 0.5rem;
            border: 1px solid #d1d5db;
        }

        .output-box pre {
            font-family: 'Courier New', monospace;
            font-size: 0.875rem;
            color: #1f2937;
            white-space: pre-wrap;
            word-wrap: break-word;
        }

        .icon {
            width: 1.25rem;
            height: 1.25rem;
            display: inline-block;
            vertical-align: middle;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Ezee Fiber</h1>
        <h2>Technical Support Note Generator</h2>

        <form id="supportForm">
            <div class="form-grid">
                <div class="form-group">
                    <label for="agentInitials">Agent Initials</label>
                    <input type="text" id="agentInitials" placeholder="Enter agent initials">
                </div>
                
                <div class="form-group">
                    <label for="phone">Phone</label>
                    <input type="text" id="phone" placeholder="Enter phone">
                </div>

                <div class="form-group">
                    <label for="name">Name</label>
                    <input type="text" id="name" placeholder="Enter name">
                </div>

                <div class="form-group">
                    <label for="address">Address</label>
                    <input type="text" id="address" placeholder="Enter address">
                </div>

                <div class="form-group">
                    <label for="salesArea">Sales Area</label>
                    <input type="text" id="salesArea" placeholder="Enter sales area">
                </div>

                <div class="form-group">
                    <label for="accountNumber">Account #</label>
                    <input type="text" id="accountNumber" placeholder="Enter account #">
                </div>

                <div class="form-group">
                    <label for="package">Package</label>
                    <input type="text" id="package" placeholder="Enter package">
                </div>
                
                <div class="form-group full-width">
                    <label for="ont">ONT Stats</label>
                    <textarea id="ont" placeholder="Enter ONT Stats: SN, Alarm codes, Light Levels, and Head End/Hub"></textarea>
                </div>

                <div class="form-group full-width">
                    <label for="customerStatement">Customer Statement</label>
                    <textarea id="customerStatement" placeholder="Enter customer statement"></textarea>
                </div>
                
                <div class="form-group full-width">
                    <label for="agentStatement">Agent Statement</label>
                    <textarea id="agentStatement" placeholder="Enter YOUR statement"></textarea>
                </div>

                <div class="form-group full-width">
                    <label for="speedTest">Speed Test (Down/Up)</label>
                    <input type="text" id="speedTest" placeholder="Enter speed test (Down/Up)">
                </div>
                
                <div class="form-group full-width">
                    <label for="l2UserAligned">L2-User Aligned (if applicable)</label>
                    <input type="text" id="l2UserAligned" placeholder="Enter L2-User aligned (if applicable)">
                </div>

                <div class="form-group">
                    <label>Are Devices Disconnecting</label>
                    <div class="yes-no-buttons">
                        <button type="button" onclick="setYesNo('devicesDisconnecting', true)">Yes</button>
                        <button type="button" onclick="setYesNo('devicesDisconnecting', false)">No</button>
                    </div>
                </div>

                <div class="form-group">
                    <label>Is Network Online?</label>
                    <div class="yes-no-buttons">
                        <button type="button" onclick="setYesNo('networkStable', true)">Yes</button>
                        <button type="button" onclick="setYesNo('networkStable', false)">No</button>
                    </div>
                </div>
                
                <div class="form-group">
                    <label>Is there Wi-Fi Channel Interference</label>
                    <div class="yes-no-buttons">
                        <button type="button" onclick="setYesNo('wifiInterference', true)">Yes</button>
                        <button type="button" onclick="setYesNo('wifiInterference', false)">No</button>
                    </div>
                </div>

                <div class="form-group">
                    <label>Was Equipment Rebooted</label>
                    <div class="yes-no-buttons">
                        <button type="button" onclick="setYesNo('equipmentRebooted', true)">Yes</button>
                        <button type="button" onclick="setYesNo('equipmentRebooted', false)">No</button>
                    </div>
                </div>

                <div class="form-group full-width">
                    <label>Are All Connections Verified</label>
                    <div class="yes-no-buttons">
                        <button type="button" onclick="setYesNo('connectionsVerified', true)">Yes</button>
                        <button type="button" onclick="setYesNo('connectionsVerified', false)">No</button>
                    </div>
                </div>

                <div class="form-group full-width">
                    <label for="timeframeIssues">Timeframe When Issues Started</label>
                    <input type="text" id="timeframeIssues" placeholder="Enter timeframe when issues started">
                </div>
            </div>
        </form>

        <div class="action-buttons">
            <button class="btn btn-primary" onclick="generateNote()">Generate Note</button>
            <button class="btn btn-secondary" onclick="resetForm()">Reset Form</button>
        </div>

        <div id="outputSection" class="output-section">
            <div class="output-header">
                <h3>Generated Note</h3>
                <button class="btn btn-success" onclick="copyToClipboard()">
                    <span id="copyIcon">📋</span>
                    <span id="copyText">Copy to Dashboard</span>
                </button>
            </div>
            <div class="output-box">
                <pre id="generatedNote"></pre>
            </div>
        </div>
    </div>

    <script>
        // Store Yes/No selections
        const yesNoData = {
            devicesDisconnecting: null,
            networkStable: null,
            wifiInterference: null,
            equipmentRebooted: null,
            connectionsVerified: null
        };

        function setYesNo(field, value) {
            yesNoData[field] = value;
            
            // Update button styles
            const buttons = event.target.parentElement.querySelectorAll('button');
            buttons.forEach(btn => {
                btn.classList.remove('active-yes', 'active-no');
            });
            
            if (value === true) {
                event.target.classList.add('active-yes');
            } else {
                event.target.classList.add('active-no');
            }
        }

        function generateNote() {
            const formData = {
                agentInitials: document.getElementById('agentInitials').value,
                accountNumber: document.getElementById('accountNumber').value,
                name: document.getElementById('name').value,
                phone: document.getElementById('phone').value,
                address: document.getElementById('address').value,
                salesArea: document.getElementById('salesArea').value,
                package: document.getElementById('package').value,
                customerStatement: document.getElementById('customerStatement').value,
                agentStatement: document.getElementById('agentStatement').value,
                ont: document.getElementById('ont').value,
                speedTest: document.getElementById('speedTest').value,
                l2UserAligned: document.getElementById('l2UserAligned').value,
                timeframeIssues: document.getElementById('timeframeIssues').value
            };

            const note = `Phone: ${formData.phone}
Agent Initials: ${formData.agentInitials}
Account #: ${formData.accountNumber}
Name: ${formData.name}
Address: ${formData.address}
Sales Area: ${formData.salesArea}
Package: ${formData.package}

Customer Statement: ${formData.customerStatement}
Agent Statement: ${formData.agentStatement}

ONT Stats: ${formData.ont}

Speed Test (Down/Up): ${formData.speedTest}
Device Connectivity Issues: ${yesNoData.devicesDisconnecting === null ? '' : yesNoData.devicesDisconnecting ? 'Yes' : 'No'}
Is Network Online: ${yesNoData.networkStable === null ? '' : yesNoData.networkStable ? 'Yes' : 'No'}
L2-User Aligned (if applicable): ${formData.l2UserAligned}
Is there Wi-Fi Channel Interference: ${yesNoData.wifiInterference === null ? '' : yesNoData.wifiInterference ? 'Yes' : 'No'}
Was Equipment Rebooted: ${yesNoData.equipmentRebooted === null ? '' : yesNoData.equipmentRebooted ? 'Yes' : 'No'}
Are All Connections Verified: ${yesNoData.connectionsVerified === null ? '' : yesNoData.connectionsVerified ? 'Yes' : 'No'}
Timeframe When Issues Started: ${formData.timeframeIssues}`;

            document.getElementById('generatedNote').textContent = note;
            document.getElementById('outputSection').classList.add('show');
            
            // Scroll to output
            document.getElementById('outputSection').scrollIntoView({ behavior: 'smooth', block: 'nearest' });
        }

        function copyToClipboard() {
            const noteText = document.getElementById('generatedNote').textContent;
            navigator.clipboard.writeText(noteText).then(() => {
                // Show success feedback
                document.getElementById('copyIcon').textContent = '✓';
                document.getElementById('copyText').textContent = 'Copied!';
                
                setTimeout(() => {
                    document.getElementById('copyIcon').textContent = '📋';
                    document.getElementById('copyText').textContent = 'Copy to Dashboard';
                }, 2000);
            });
        }

        function resetForm() {
            document.getElementById('supportForm').reset();
            
            // Reset Yes/No data
            Object.keys(yesNoData).forEach(key => {
                yesNoData[key] = null;
            });
            
            // Remove active classes from all Yes/No buttons
            document.querySelectorAll('.yes-no-buttons button').forEach(btn => {
                btn.classList.remove('active-yes', 'active-no');
            });
            
            // Hide output section
            document.getElementById('outputSection').classList.remove('show');
        }
    </script>
</body>
</html>
