import React, { useState } from 'react';
import jsonData from './data.json';

const App = () => {
  const [selectedCountry, setSelectedCountry] = useState('');
  const [selectedState, setSelectedState] = useState('');
  const [selectedCities, setSelectedCities] = useState([]);

  const handleCountryChange = (e) => {
    setSelectedCountry(e.target.value);
    setSelectedState('');
    setSelectedCities([]);
  };

  const handleStateChange = (e) => {
    setSelectedState(e.target.value);
    setSelectedCities([]);
  };

  const handleCityChange = (e) => {
    const selectedCityIds = Array.from(e.target.options)
      .filter((option) => option.selected)
      .map((option) => option.value);

    setSelectedCities(selectedCityIds);
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    console.log('Selected Country:', selectedCountry);
    console.log('Selected State:', selectedState);
    console.log('Selected Cities:', selectedCities);
  };

  const getStatesByCountry = (country) => {
    const selectedCountryData = jsonData.find((item) => item.country.toLowerCase() === country.toLowerCase());
    if (selectedCountryData) {
      return selectedCountryData.state.map((state) => state.state);
    }
    return [];
  };

  const getCitiesByState = (state) => {
    const selectedCountryData = jsonData.find((item) => item.country.toLowerCase() === selectedCountry.toLowerCase());
    if (selectedCountryData) {
      const selectedStateData = selectedCountryData.state.find((item) => item.state.toLowerCase() === state.toLowerCase());
      if (selectedStateData) {
        return selectedStateData.city.map((city) => city.name);
      }
    }
    return [];
  };

  return (
    <div>
      <h1>Dynamic Dropdown</h1>
      <form onSubmit={handleSubmit}>
        <label htmlFor="country">Country:</label>
        <select id="country" value={selectedCountry} onChange={handleCountryChange}>
          <option value="">Select Country</option>
          {jsonData.map((item) => (
            <option key={item.id} value={item.country}>
              {item.country}
            </option>
          ))}
        </select>

        {selectedCountry && (
          <>
            <label htmlFor="state">State:</label>
            <select id="state" value={selectedState} onChange={handleStateChange}>
              <option value="">Select State</option>
              {getStatesByCountry(selectedCountry).map((state) => (
                <option key={state} value={state}>
                  {state}
                </option>
              ))}
            </select>
          </>
        )}

        {selectedState && (
          <>
            <label htmlFor="cities">Cities:</label>
            <select id="cities" multiple value={selectedCities} onChange={handleCityChange}>
              {getCitiesByState(selectedState).map((city) => (
                <option key={city} value={city}>
                  {city}
                </option>
              ))}
            </select>
          </>
        )}

        <button type="submit">Submit</button>
      </form>
    </div>
  );
};

export default App;
