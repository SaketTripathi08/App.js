// src/App.js
import React, { useState } from 'react';
import axios from 'axios';
import './App.css';

function App() {
    const [input, setInput] = useState('');
    const [response, setResponse] = useState(null);
    const [selectedOptions, setSelectedOptions] = useState([]);

    const handleSubmit = async () => {
        try {
            const res = await axios.post('https://your-heroku-app.herokuapp.com/bfhl', JSON.parse(input));
            setResponse(res.data);
        } catch (error) {
            console.error('Error:', error);
        }
    };

    const handleSelectChange = (e) => {
        const value = Array.from(e.target.selectedOptions, option => option.value);
        setSelectedOptions(value);
    };

    return (
        <div className="App">
            <h1>ABCD123</h1>
            <textarea value={input} onChange={(e) => setInput(e.target.value)} placeholder='Enter JSON here'></textarea>
            <button onClick={handleSubmit}>Submit</button>
            <br />
            <select multiple={true} value={selectedOptions} onChange={handleSelectChange}>
                <option value="numbers">Numbers</option>
                <option value="alphabets">Alphabets</option>
                <option value="highest_alphabet">Highest Alphabet</option>
            </select>
            <div>
                {response && (
                    <div>
                        {selectedOptions.includes('numbers') && <p>Numbers: {response.numbers.join(', ')}</p>}
                        {selectedOptions.includes('alphabets') && <p>Alphabets: {response.alphabets.join(', ')}</p>}
                        {selectedOptions.includes('highest_alphabet') && <p>Highest Alphabet: {response.highest_alphabet.join(', ')}</p>}
                    </div>
                )}
            </div>
        </div>
    );
}

export default App;
