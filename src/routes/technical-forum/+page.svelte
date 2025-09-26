<script>
  let name = "";
  let employeeCode = "";
  let email = "";
  let telephone = "";
  let subject = "";
  let query = "";
  let file;

  function handleSubmit(event) {
    event.preventDefault();

    console.log({
      name,
      employeeCode,
      email,
      telephone,
      subject,
      file,
      query
    });

    alert("Form submitted! (check console)");
  }
</script>

<div class="max-w-2xl mx-auto bg-white p-8 mt-6 rounded-2xl shadow-lg border border-gray-200">
  <h2 class="text-3xl font-semibold mb-6 text-gray-800 border-b pb-3">Technical Forum</h2>

  <form on:submit={handleSubmit} class="space-y-5">
    <!-- Name -->
    <div>
      <label class="block text-sm font-medium text-gray-700 mb-1">Name</label>
      <input
        type="text"
        bind:value={name}
        class="w-full border border-gray-300 rounded-lg px-3 py-2 focus:ring-2 focus:ring-blue-500 focus:outline-none"
        required
      />
    </div>

    <!-- Employee Code -->
    <div>
      <label class="block text-sm font-medium text-gray-700 mb-1">Employee Code</label>
      <input
        type="text"
        bind:value={employeeCode}
        class="w-full border border-gray-300 rounded-lg px-3 py-2 focus:ring-2 focus:ring-blue-500 focus:outline-none"
        required
      />
    </div>

    <!-- Email -->
    <div>
      <label class="block text-sm font-medium text-gray-700 mb-1">Email ID</label>
      <input
        type="email"
        bind:value={email}
        class="w-full border border-gray-300 rounded-lg px-3 py-2 focus:ring-2 focus:ring-blue-500 focus:outline-none"
        required
      />
    </div>

    <!-- Telephone Ext -->
    <div>
      <label class="block text-sm font-medium text-gray-700 mb-1">Telephone Ext</label>
      <input
        type="text"
        bind:value={telephone}
        class="w-full border border-gray-300 rounded-lg px-3 py-2 focus:ring-2 focus:ring-blue-500 focus:outline-none"
      />
    </div>

    <!-- Subject -->
    <div>
      <label class="block text-sm font-medium text-gray-700 mb-1">Subject</label>
      <input
        type="text"
        bind:value={subject}
        class="w-full border border-gray-300 rounded-lg px-3 py-2 focus:ring-2 focus:ring-blue-500 focus:outline-none"
        required
      />
    </div>

    <!-- Attach File -->
    <div>
      <label class="block text-sm font-medium text-gray-700 mb-1">Attach File (.zip preferred)</label>
      <input
        type="file"
        accept=".zip,.rar,.7z,.tar,.gz"
        class="block w-full text-sm text-gray-600 file:mr-4 file:py-2 file:px-4 file:rounded-lg file:border-0 file:text-sm file:font-medium file:bg-blue-50 file:text-blue-700 hover:file:bg-blue-100"
        on:change={(e) => (file = e.target.files[0])}
      />
    </div>

    <!-- Query -->
    <div>
      <label class="block text-sm font-medium text-gray-700 mb-1">Type your queries here</label>
      <textarea
        bind:value={query}
        class="w-full border border-gray-300 rounded-lg px-3 py-2 h-32 focus:ring-2 focus:ring-blue-500 focus:outline-none"
        required
      ></textarea>
    </div>

    <!-- Submit Button -->
    <div class="pt-2">
      <button
        type="submit"
        class="w-full bg-blue-600 text-white font-medium py-2.5 rounded-lg hover:bg-blue-700 transition duration-200"
      >
        Submit Query
      </button>
    </div>
  </form>
</div>
